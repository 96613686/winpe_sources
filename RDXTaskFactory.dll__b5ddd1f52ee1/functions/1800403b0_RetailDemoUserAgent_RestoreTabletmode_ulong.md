# RetailDemoUserAgent::RestoreTabletmode(ulong)

- ea: `0x1800403b0`
- end: `0x1800404ee`
- name: `?RestoreTabletmode@RetailDemoUserAgent@@UEAAJK@Z`
- size: `318`
- prototype: `__int64 __fastcall(RetailDemoUserAgent *__hidden this, unsigned int)`
- caller_count: `0`
- callee_count: `4`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callees

- `0x180008bbc`
- `0x18000aa7c`
- `0x1800403b0`
- `0x180050010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1800403f1`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1800403f1`

## string_xrefs

- `0x180040404`: `pcshell\shell\retaildemo\desktoptaskfactory\retaildemouseragent\service\retaildemouseragent.cpp`
- `0x180040461`: `pcshell\shell\retaildemo\desktoptaskfactory\retaildemouseragent\service\retaildemouseragent.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall RetailDemoUserAgent::RestoreTabletmode(RetailDemoUserAgent *this, __int64 a2, __int64 a3)
{
  unsigned int v3; // esi
  HRESULT Instance; // eax
  __int64 v5; // rdx
  __int64 v6; // r8
  unsigned int v7; // ebx
  __int64 v8; // rdx
  __int64 v9; // r8
  LPVOID v10; // rdi
  __int64 (__fastcall *v11)(LPVOID, GUID *, GUID *, __int64 *); // rbx
  int v12; // eax
  __int64 v13; // rdx
  __int64 v14; // rdx
  __int64 v15; // r8
  __int64 v16; // rdx
  __int64 v17; // r8
  int ppv; // [rsp+20h] [rbp-20h]
  LPVOID v20[2]; // [rsp+30h] [rbp-10h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+58h] [rbp+18h]
  int v22; // [rsp+70h] [rbp+30h] BYREF
  __int64 v23; // [rsp+78h] [rbp+38h] BYREF

  v3 = a2;
  v20[0] = 0;
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(v20, a2, a3);
  Instance = CoCreateInstance(&CLSID_ImmersiveShell, 0, 0x404u, &GUID_6d5140c1_7436_11ce_8034_00aa006009fa, v20);
  v7 = Instance;
  if ( Instance >= 0 )
  {
    v23 = 0;
    v10 = v20[0];
    v11 = *(__int64 (__fastcall **)(LPVOID, GUID *, GUID *, __int64 *))(*(_QWORD *)v20[0] + 24LL);
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v23, v5, v6);
    v12 = v11(v10, &GUID_4fda780a_acd2_41f7_b4f2_ebe674c9bf2a, &GUID_4fda780a_acd2_41f7_b4f2_ebe674c9bf2a, &v23);
    v7 = v12;
    if ( v12 >= 0 )
    {
      v22 = 0;
      v12 = (*(__int64 (__fastcall **)(__int64, int *))(*(_QWORD *)v23 + 24LL))(v23, &v22);
      v7 = v12;
      if ( v12 >= 0 )
      {
        if ( v3 == v22
          || (v12 = (*(__int64 (__fastcall **)(__int64, _QWORD, __int64))(*(_QWORD *)v23 + 32LL))(v23, v3, 9),
              v7 = v12,
              v12 >= 0) )
        {
          Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v23, v16, v17);
          v7 = 0;
          goto LABEL_12;
        }
        v13 = 2138;
      }
      else
      {
        v13 = 2134;
      }
    }
    else
    {
      v13 = 2131;
    }
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v13,
      (unsigned int)"pcshell\\shell\\retaildemo\\desktoptaskfactory\\retaildemouseragent\\service\\retaildemouseragent.cpp",
      (const char *)(unsigned int)v12,
      ppv);
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v23, v14, v15);
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x850,
      (unsigned int)"pcshell\\shell\\retaildemo\\desktoptaskfactory\\retaildemouseragent\\service\\retaildemouseragent.cpp",
      (const char *)(unsigned int)Instance,
      ppv);
  }
LABEL_12:
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(v20, v8, v9);
  return v7;
}

```

## disassembly

```asm
0x1800403b0  mov     [rsp-18h+arg_0], rbx
0x1800403b5  push    rbp
0x1800403b6  push    rsi
0x1800403b7  push    rdi
0x1800403b8  mov     rbp, rsp
0x1800403bb  sub     rsp, 40h
0x1800403bf  mov     esi, edx
0x1800403c1  mov     [rbp+var_10], 0
0x1800403c9  lea     rcx, [rbp+var_10]
0x1800403cd  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800403d2  lea     rax, [rbp+var_10]
0x1800403d6  mov     qword ptr [rsp+40h+ppv], rax; int
0x1800403db  lea     r9, _GUID_6d5140c1_7436_11ce_8034_00aa006009fa; riid
0x1800403e2  xor     edx, edx; pUnkOuter
0x1800403e4  mov     r8d, 404h; dwClsContext
0x1800403ea  lea     rcx, CLSID_ImmersiveShell; rclsid
0x1800403f1  call    cs:__imp_CoCreateInstance
0x1800403f7  mov     ebx, eax
0x1800403f9  test    eax, eax
0x1800403fb  jns     short loc_18004041A
0x1800403fd  mov     rcx, [rbp+18h]; this
0x180040401  mov     r9d, eax; char *
0x180040404  lea     r8, aPcshellShellRe_31; "pcshell\\shell\\retaildemo\\desktoptask"...
0x18004040b  mov     edx, 850h; void *
0x180040410  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180040415  jmp     loc_1800404D6
0x18004041a  mov     [rbp+arg_18], 0
0x180040422  mov     rdi, [rbp+var_10]
0x180040426  mov     rax, [rdi]
0x180040429  mov     rbx, [rax+18h]
0x18004042d  lea     rcx, [rbp+arg_18]
0x180040431  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180040436  lea     r9, [rbp+arg_18]
0x18004043a  lea     rdx, _GUID_4fda780a_acd2_41f7_b4f2_ebe674c9bf2a
0x180040441  mov     r8, rdx
0x180040444  mov     rcx, rdi
0x180040447  mov     rax, rbx
0x18004044a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004044f  mov     ebx, eax
0x180040451  test    eax, eax
0x180040453  jns     short loc_180040479
0x180040455  mov     edx, 853h; void *
0x18004045a  mov     rcx, [rbp+18h]; this
0x18004045e  mov     r9d, eax; char *
0x180040461  lea     r8, aPcshellShellRe_31; "pcshell\\shell\\retaildemo\\desktoptask"...
0x180040468  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18004046d  nop
0x18004046e  lea     rcx, [rbp+arg_18]
0x180040472  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180040477  jmp     short loc_1800404D6
0x180040479  mov     [rbp+arg_10], 0
0x180040480  mov     rcx, [rbp+arg_18]
0x180040484  mov     rax, [rcx]
0x180040487  lea     rdx, [rbp+arg_10]
0x18004048b  mov     rax, [rax+18h]
0x18004048f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180040494  mov     ebx, eax
0x180040496  test    eax, eax
0x180040498  jns     short loc_1800404A1
0x18004049a  mov     edx, 856h
0x18004049f  jmp     short loc_18004045A
0x1800404a1  cmp     esi, [rbp+arg_10]
0x1800404a4  jz      short loc_1800404CB
0x1800404a6  mov     rcx, [rbp+arg_18]
0x1800404aa  mov     rax, [rcx]
0x1800404ad  mov     r8d, 9
0x1800404b3  mov     edx, esi
0x1800404b5  mov     rax, [rax+20h]
0x1800404b9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800404be  mov     ebx, eax
0x1800404c0  test    eax, eax
0x1800404c2  jns     short loc_1800404CB
0x1800404c4  mov     edx, 85Ah
0x1800404c9  jmp     short loc_18004045A
0x1800404cb  lea     rcx, [rbp+arg_18]
0x1800404cf  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800404d4  xor     ebx, ebx
0x1800404d6  lea     rcx, [rbp+var_10]
0x1800404da  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800404df  mov     eax, ebx
0x1800404e1  mov     rbx, [rsp+40h+arg_0]
0x1800404e6  add     rsp, 40h
0x1800404ea  pop     rdi
0x1800404eb  pop     rsi
0x1800404ec  pop     rbp
0x1800404ed  retn
```
