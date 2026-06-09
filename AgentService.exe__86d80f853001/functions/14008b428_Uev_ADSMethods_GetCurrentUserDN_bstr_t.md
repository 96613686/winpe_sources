# Uev::ADSMethods::GetCurrentUserDN(_bstr_t &)

- ea: `0x14008b428`
- end: `0x14008b50e`
- name: `?GetCurrentUserDN@ADSMethods@Uev@@CAJAEAV_bstr_t@@@Z`
- size: `230`
- prototype: `__int64 __fastcall(struct _bstr_t *this)`
- caller_count: `1`
- callee_count: `6`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x14008ace0`

## callees

- `0x140003e50`
- `0x140003e74`
- `0x1400663e4`
- `0x140087a7c`
- `0x14008b428`
- `0x14009b010`

## import_xrefs

- `ole32!CoCreateInstance` at `0x14008b46e`
- `ole32!CoCreateInstance` at `0x14008b46e`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall Uev::ADSMethods::GetCurrentUserDN(struct _bstr_t *this)
{
  unsigned int Instance; // ebx
  __int64 *v3; // rbx
  __int64 v4; // rsi
  _QWORD *v5; // rax
  __int64 *v7; // [rsp+38h] [rbp-20h] BYREF

  v7 = 0;
  Instance = CoCreateInstance(&CLSID_ADSystemInfo, 0, 1u, &GUID_5bb11929_afd1_11d2_9cb9_0000f87a369e, (LPVOID *)&v7);
  if ( !Instance )
  {
    v3 = v7;
    v4 = *v7;
    _bstr_t::_Free(this);
    v5 = operator new(0x18u);
    if ( v5 )
    {
      v5[1] = 0;
      *((_DWORD *)v5 + 4) = 1;
      *v5 = 0;
    }
    *(_QWORD *)this = v5;
    if ( !v5 )
      _com_issue_error(-2147024882);
    Instance = (*(__int64 (__fastcall **)(__int64 *, _QWORD *))(v4 + 56))(v3, v5);
  }
  if ( v7 )
    (*(void (__fastcall **)(__int64 *))(*v7 + 16))(v7);
  return Instance;
}

```

## disassembly

```asm
0x14008b428  mov     r11, rsp
0x14008b42b  mov     [r11+10h], rbx
0x14008b42f  mov     [r11+18h], rsi
0x14008b433  push    rdi
0x14008b434  sub     rsp, 50h
0x14008b438  mov     rax, cs:__security_cookie
0x14008b43f  xor     rax, rsp
0x14008b442  mov     [rsp+58h+var_18], rax
0x14008b447  mov     rdi, rcx
0x14008b44a  mov     qword ptr [r11-20h], 0
0x14008b452  lea     rax, [r11-20h]
0x14008b456  mov     [r11-38h], rax
0x14008b45a  lea     r9, _GUID_5bb11929_afd1_11d2_9cb9_0000f87a369e; riid
0x14008b461  xor     edx, edx; pUnkOuter
0x14008b463  lea     r8d, [rdx+1]; dwClsContext
0x14008b467  lea     rcx, CLSID_ADSystemInfo; rclsid
0x14008b46e  call    cs:__imp_CoCreateInstance
0x14008b474  mov     ebx, eax
0x14008b476  test    eax, eax
0x14008b478  jnz     short loc_14008B4CD
0x14008b47a  mov     rbx, [rsp+58h+var_20]
0x14008b47f  mov     rsi, [rbx]
0x14008b482  mov     rcx, rdi; this
0x14008b485  call    ?_Free@_bstr_t@@AEAAXXZ; _bstr_t::_Free(void)
0x14008b48a  mov     ecx, 18h; Size
0x14008b48f  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x14008b494  mov     [rsp+58h+var_28], rax
0x14008b499  test    rax, rax
0x14008b49c  jz      short loc_14008B4B4
0x14008b49e  mov     qword ptr [rax+8], 0
0x14008b4a6  mov     dword ptr [rax+10h], 1
0x14008b4ad  mov     qword ptr [rax], 0
0x14008b4b4  mov     [rdi], rax
0x14008b4b7  test    rax, rax
0x14008b4ba  jz      short loc_14008B503
0x14008b4bc  mov     rdx, rax
0x14008b4bf  mov     rcx, rbx
0x14008b4c2  mov     rax, [rsi+38h]
0x14008b4c6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14008b4cb  mov     ebx, eax
0x14008b4cd  mov     rcx, [rsp+58h+var_20]
0x14008b4d2  test    rcx, rcx
0x14008b4d5  jz      short loc_14008B4E4
0x14008b4d7  mov     rax, [rcx]
0x14008b4da  mov     rax, [rax+10h]
0x14008b4de  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14008b4e3  nop
0x14008b4e4  mov     eax, ebx
0x14008b4e6  mov     rcx, [rsp+58h+var_18]
0x14008b4eb  xor     rcx, rsp; StackCookie
0x14008b4ee  call    __security_check_cookie
0x14008b4f3  mov     rbx, [rsp+58h+arg_8]
0x14008b4f8  mov     rsi, [rsp+58h+arg_10]
0x14008b4fd  add     rsp, 50h
0x14008b501  pop     rdi
0x14008b502  retn
0x14008b503  mov     ecx, 8007000Eh; int
0x14008b508  call    ?_com_issue_error@@YAXJ@Z; _com_issue_error(long)
```
