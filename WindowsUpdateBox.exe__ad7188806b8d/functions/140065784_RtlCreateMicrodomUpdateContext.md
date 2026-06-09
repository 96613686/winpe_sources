# RtlCreateMicrodomUpdateContext

- ea: `0x140065784`
- end: `0x14006590f`
- name: `RtlCreateMicrodomUpdateContext`
- size: `395`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD)`
- caller_count: `5`
- callee_count: `4`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x14005c180`
- `0x14005de84`
- `0x14005ec68`
- `0x14005f680`
- `0x140060960`

## callees

- `0x140062958`
- `0x140063314`
- `0x140065784`
- `0x140072764`

## import_xrefs

- `KERNEL32!HeapFree` at `0x1400658ec`
- `KERNEL32!HeapFree` at `0x1400658ec`
- `KERNEL32!HeapAlloc` at `0x14006582d`
- `KERNEL32!HeapAlloc` at `0x14006582d`
- `KERNEL32!GetProcessHeap` at `0x140065818`
- `KERNEL32!GetProcessHeap` at `0x1400658d8`
- `KERNEL32!GetProcessHeap` at `0x140065818`
- `KERNEL32!GetProcessHeap` at `0x1400658d8`

## string_xrefs

- `0x1400657aa`: `onecore\base\xml\udom_modify.cpp`
- `0x1400657f1`: `onecore\base\xml\udom_modify.cpp`
- `0x140065880`: `onecore\base\xml\udom_modify.cpp`
- `0x1400657bd`: `Windows::uDom::Rtl::RtlCreateMicrodomUpdateContext`
- `0x140065804`: `Windows::uDom::Rtl::RtlCreateMicrodomUpdateContext`
- `0x140065897`: `Windows::uDom::Rtl::RtlCreateMicrodomUpdateContext`
- `0x14006580f`: `Not-null check failed: UpdateContext`

## pseudocode

```c
__int64 __fastcall RtlCreateMicrodomUpdateContext(
        __int64 a1,
        struct Windows::Microdom::Rtl::IRtlMicrodom *a2,
        struct CChildNode ***a3)
{
  const char *v5; // rax
  HANDLE ProcessHeap; // rax
  _QWORD *v8; // rax
  __int64 v9; // rdx
  struct CChildNode **v10; // rbx
  _QWORD *v11; // rax
  int v12; // esi
  HANDLE v13; // rax
  const char *v14; // [rsp+20h] [rbp-20h] BYREF
  const char *v15; // [rsp+28h] [rbp-18h]
  __int64 v16; // [rsp+30h] [rbp-10h]
  const char *v17; // [rsp+38h] [rbp-8h]

  if ( a3 )
    *a3 = 0;
  if ( !a2 )
  {
    v16 = 1424;
    v14 = "onecore\\base\\xml\\udom_modify.cpp";
    v15 = "Windows::uDom::Rtl::RtlCreateMicrodomUpdateContext";
    v5 = "SourceMicrodom != 0";
LABEL_5:
    v17 = v5;
    RtlReportErrorOrigination(&v14, a2, 3221225485LL);
    return 3221225485LL;
  }
  if ( !a3 )
  {
    v16 = 1425;
    v14 = "onecore\\base\\xml\\udom_modify.cpp";
    v15 = "Windows::uDom::Rtl::RtlCreateMicrodomUpdateContext";
    v5 = "Not-null check failed: UpdateContext";
    goto LABEL_5;
  }
  ProcessHeap = GetProcessHeap();
  v8 = HeapAlloc(ProcessHeap, 0, 0x40u);
  v10 = (struct CChildNode **)v8;
  if ( v8 )
  {
    *v8 = 0;
    v11 = v8 + 1;
    v10[5] = 0;
    v10[6] = 0;
    v10[7] = 0;
    v11[3] = 0;
    *v11 = v11;
    v11[1] = v11;
    v11[2] = v11;
  }
  else
  {
    v10 = 0;
  }
  if ( v10 )
  {
    v12 = CMicrodomUpdateContext::Construct(v10, a2);
    if ( v12 >= 0 )
    {
      *a3 = v10;
      return 0;
    }
    else
    {
      CMicrodomUpdateContext::~CMicrodomUpdateContext((CMicrodomUpdateContext *)v10);
      v13 = GetProcessHeap();
      HeapFree(v13, 0, v10);
      return (unsigned int)v12;
    }
  }
  else
  {
    v16 = 1433;
    v14 = "onecore\\base\\xml\\udom_modify.cpp";
    v15 = "Windows::uDom::Rtl::RtlCreateMicrodomUpdateContext";
    v17 = "NewContext.Allocate()";
    RtlReportErrorOrigination(&v14, v9, 3221225495LL);
    return 3221225495LL;
  }
}

```

## disassembly

```asm
0x140065784  mov     [rsp-18h+arg_0], rbx
0x140065789  push    rbp
0x14006578a  push    rsi
0x14006578b  push    rdi
0x14006578c  mov     rbp, rsp
0x14006578f  sub     rsp, 40h
0x140065793  mov     rdi, r8
0x140065796  mov     rsi, rdx
0x140065799  test    r8, r8
0x14006579c  jz      short loc_1400657A5
0x14006579e  mov     qword ptr [r8], 0
0x1400657a5  test    rsi, rsi
0x1400657a8  jnz     short loc_1400657EC
0x1400657aa  lea     rax, aOnecoreBaseXml; "onecore\\base\\xml\\udom_modify.cpp"
0x1400657b1  mov     [rbp+var_10], 590h
0x1400657b9  mov     [rbp+var_20], rax
0x1400657bd  lea     rax, aWindowsUdomRtl_3; "Windows::uDom::Rtl::RtlCreateMicrodomUp"...
0x1400657c4  mov     [rbp+var_18], rax
0x1400657c8  lea     rax, aSourcemicrodom; "SourceMicrodom != 0"
0x1400657cf  mov     r8d, 0C000000Dh
0x1400657d5  mov     [rbp+var_8], rax
0x1400657d9  lea     rcx, [rbp+var_20]
0x1400657dd  call    RtlReportErrorOrigination
0x1400657e2  mov     eax, 0C000000Dh
0x1400657e7  jmp     loc_140065901
0x1400657ec  test    rdi, rdi
0x1400657ef  jnz     short loc_140065818
0x1400657f1  lea     rax, aOnecoreBaseXml; "onecore\\base\\xml\\udom_modify.cpp"
0x1400657f8  mov     [rbp+var_10], 591h
0x140065800  mov     [rbp+var_20], rax
0x140065804  lea     rax, aWindowsUdomRtl_3; "Windows::uDom::Rtl::RtlCreateMicrodomUp"...
0x14006580b  mov     [rbp+var_18], rax
0x14006580f  lea     rax, aNotNullCheckFa_10; "Not-null check failed: UpdateContext"
0x140065816  jmp     short loc_1400657CF
0x140065818  call    cs:__imp_GetProcessHeap
0x14006581f  nop     dword ptr [rax+rax+00h]
0x140065824  xor     edx, edx; dwFlags
0x140065826  mov     rcx, rax; hHeap
0x140065829  lea     r8d, [rdx+40h]; dwBytes
0x14006582d  call    cs:__imp_HeapAlloc
0x140065834  nop     dword ptr [rax+rax+00h]
0x140065839  mov     rbx, rax
0x14006583c  test    rax, rax
0x14006583f  jz      short loc_140065879
0x140065841  mov     qword ptr [rax], 0
0x140065848  add     rax, 8
0x14006584c  mov     qword ptr [rbx+28h], 0
0x140065854  mov     qword ptr [rbx+30h], 0
0x14006585c  mov     qword ptr [rbx+38h], 0
0x140065864  mov     qword ptr [rax+18h], 0
0x14006586c  mov     [rax], rax
0x14006586f  mov     [rax+8], rax
0x140065873  mov     [rax+10h], rax
0x140065877  jmp     short loc_14006587B
0x140065879  xor     ebx, ebx
0x14006587b  test    rbx, rbx
0x14006587e  jnz     short loc_1400658BF
0x140065880  lea     rax, aOnecoreBaseXml; "onecore\\base\\xml\\udom_modify.cpp"
0x140065887  mov     [rbp+var_10], 599h
0x14006588f  mov     [rbp+var_20], rax
0x140065893  lea     rcx, [rbp+var_20]
0x140065897  lea     rax, aWindowsUdomRtl_3; "Windows::uDom::Rtl::RtlCreateMicrodomUp"...
0x14006589e  mov     r8d, 0C0000017h
0x1400658a4  mov     [rbp+var_18], rax
0x1400658a8  lea     rax, aNewcontextAllo; "NewContext.Allocate()"
0x1400658af  mov     [rbp+var_8], rax
0x1400658b3  call    RtlReportErrorOrigination
0x1400658b8  mov     eax, 0C0000017h
0x1400658bd  jmp     short loc_140065901
0x1400658bf  mov     rdx, rsi; struct Windows::Microdom::Rtl::IRtlMicrodom *
0x1400658c2  mov     rcx, rbx; this
0x1400658c5  call    ?Construct@CMicrodomUpdateContext@@QEAAJPEAUIRtlMicrodom@Rtl@Microdom@Windows@@@Z; CMicrodomUpdateContext::Construct(Windows::Microdom::Rtl::IRtlMicrodom *)
0x1400658ca  mov     esi, eax
0x1400658cc  test    eax, eax
0x1400658ce  jns     short loc_1400658FC
0x1400658d0  mov     rcx, rbx; this
0x1400658d3  call    ??1CMicrodomUpdateContext@@QEAA@XZ; CMicrodomUpdateContext::~CMicrodomUpdateContext(void)
0x1400658d8  call    cs:__imp_GetProcessHeap
0x1400658df  nop     dword ptr [rax+rax+00h]
0x1400658e4  mov     r8, rbx; lpMem
0x1400658e7  xor     edx, edx; dwFlags
0x1400658e9  mov     rcx, rax; hHeap
0x1400658ec  call    cs:__imp_HeapFree
0x1400658f3  nop     dword ptr [rax+rax+00h]
0x1400658f8  mov     eax, esi
0x1400658fa  jmp     short loc_140065901
0x1400658fc  mov     [rdi], rbx
0x1400658ff  xor     eax, eax
0x140065901  mov     rbx, [rsp+40h+arg_0]
0x140065906  add     rsp, 40h
0x14006590a  pop     rdi
0x14006590b  pop     rsi
0x14006590c  pop     rbp
0x14006590d  retn
```
