# APPPOOL_CUSTOM_PROVIDER::HandleAppPoolCommand(PROPERTY_ENTRY *)

- ea: `0x1800194dc`
- end: `0x180019674`
- name: `?HandleAppPoolCommand@APPPOOL_CUSTOM_PROVIDER@@AEAAJPEAVPROPERTY_ENTRY@@@Z`
- size: `408`
- prototype: `__int64 __fastcall(APPPOOL_CUSTOM_PROVIDER *__hidden this, struct PROPERTY_ENTRY *)`
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callers

- `0x1800197a0`

## callees

- `0x1800194dc`
- `0x1800271e4`
- `0x18002c010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180019531`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180019531`
- `iisutil!?QueryPtr@BUFFER@@QEBAPEAXXZ` at `0x180019543`
- `iisutil!?QueryPtr@BUFFER@@QEBAPEAXXZ` at `0x180019543`

## pseudocode

```c
__int64 __fastcall APPPOOL_CUSTOM_PROVIDER::HandleAppPoolCommand(
        APPPOOL_CUSTOM_PROVIDER *this,
        struct PROPERTY_ENTRY *a2)
{
  HRESULT v4; // eax
  int v5; // ebx
  int v6; // eax
  __int64 v7; // rax
  __int64 (*v8)(void); // rax
  unsigned int v9; // ebx
  LPVOID ppv; // [rsp+58h] [rbp+28h] BYREF
  __int64 *v12; // [rsp+60h] [rbp+30h] BYREF
  __int64 v13; // [rsp+68h] [rbp+38h] BYREF

  v12 = 0;
  ppv = 0;
  v13 = 0;
  if ( a2 )
  {
    v4 = CoCreateInstance(&CLSID_RSCA_WAS, 0, 0x15u, &IID_IRSCA_WAS, &ppv);
    if ( v4 >= 0 )
    {
      v5 = **((_DWORD **)BUFFER::QueryPtr((struct PROPERTY_ENTRY *)((char *)a2 + 16)) + 3);
      v4 = (*(__int64 (__fastcall **)(_QWORD, const wchar_t *, bool, _QWORD))(**((_QWORD **)this + 3) + 136LL))(
             *((_QWORD *)this + 3),
             L"autoStart",
             v5 == 1,
             0);
      if ( v4 >= 0 )
      {
        v4 = (*(__int64 (__fastcall **)(_QWORD, const wchar_t *, __int64 *, _QWORD, _QWORD))(**((_QWORD **)this + 3)
                                                                                           + 64LL))(
               *((_QWORD *)this + 3),
               L"name",
               &v13,
               0,
               0);
        if ( v4 >= 0 )
        {
          v4 = (*(__int64 (__fastcall **)(LPVOID, _QWORD))(*(_QWORD *)ppv + 24LL))(ppv, 0);
          if ( v4 >= 0 )
          {
            v6 = (*(__int64 (__fastcall **)(LPVOID, __int64, __int64 **))(*(_QWORD *)ppv + 32LL))(ppv, v13, &v12);
            if ( v6 >= 0
              || v6 == -2147024891
              && (int)StartIISService(L"WAS") >= 0
              && (*(int (__fastcall **)(LPVOID, __int64, __int64 **))(*(_QWORD *)ppv + 32LL))(ppv, v13, &v12) >= 0 )
            {
              v7 = *v12;
              if ( v5 == 1 )
                v8 = *(__int64 (**)(void))(v7 + 40);
              else
                v8 = *(__int64 (**)(void))(v7 + 48);
              v4 = v8();
            }
            else
            {
              v4 = 0;
            }
          }
        }
      }
    }
  }
  else
  {
    v4 = -2147024809;
  }
  v9 = 0;
  if ( v4 >= 0 )
    v9 = v4;
  if ( ppv )
  {
    (*(void (**)(void))(*(_QWORD *)ppv + 16LL))();
    ppv = 0;
  }
  if ( v12 )
    (*(void (__fastcall **)(__int64 *))(*v12 + 16))(v12);
  return v9;
}

```

## disassembly

```asm
0x1800194dc  push    rbp
0x1800194de  push    rbx
0x1800194df  push    rdi
0x1800194e0  mov     rbp, rsp
0x1800194e3  sub     rsp, 30h
0x1800194e7  mov     [rbp+arg_10], 0
0x1800194ef  mov     rbx, rdx
0x1800194f2  mov     [rbp+arg_8], 0
0x1800194fa  mov     rdi, rcx
0x1800194fd  mov     [rbp+arg_18], 0
0x180019505  test    rdx, rdx
0x180019508  jnz     short loc_180019514
0x18001950a  mov     eax, 80070057h
0x18001950f  jmp     loc_180019631
0x180019514  xor     edx, edx; pUnkOuter
0x180019516  lea     rax, [rbp+arg_8]
0x18001951a  lea     r9, IID_IRSCA_WAS; riid
0x180019521  mov     [rsp+30h+ppv], rax; ppv
0x180019526  lea     rcx, CLSID_RSCA_WAS; rclsid
0x18001952d  lea     r8d, [rdx+15h]; dwClsContext
0x180019531  call    cs:__imp_CoCreateInstance
0x180019537  test    eax, eax
0x180019539  js      loc_180019631
0x18001953f  lea     rcx, [rbx+10h]
0x180019543  call    cs:__imp_?QueryPtr@BUFFER@@QEBAPEAXXZ; BUFFER::QueryPtr(void)
0x180019549  xor     r8d, r8d
0x18001954c  lea     rdx, aAutostart; "autoStart"
0x180019553  mov     rcx, [rax+18h]
0x180019557  mov     ebx, [rcx]
0x180019559  cmp     ebx, 1
0x18001955c  mov     rcx, [rdi+18h]
0x180019560  setz    r8b
0x180019564  xor     r9d, r9d
0x180019567  mov     rax, [rcx]
0x18001956a  mov     rax, [rax+88h]
0x180019571  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180019576  test    eax, eax
0x180019578  js      loc_180019631
0x18001957e  mov     rcx, [rdi+18h]
0x180019582  lea     r8, [rbp+arg_18]
0x180019586  xor     r9d, r9d
0x180019589  mov     [rsp+30h+ppv], 0
0x180019592  lea     rdx, aName; "name"
0x180019599  mov     rax, [rcx]
0x18001959c  mov     rax, [rax+40h]
0x1800195a0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800195a5  test    eax, eax
0x1800195a7  js      loc_180019631
0x1800195ad  mov     rcx, [rbp+arg_8]
0x1800195b1  xor     edx, edx
0x1800195b3  mov     rax, [rcx]
0x1800195b6  mov     rax, [rax+18h]
0x1800195ba  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800195bf  test    eax, eax
0x1800195c1  js      short loc_180019631
0x1800195c3  mov     rcx, [rbp+arg_8]
0x1800195c7  lea     r8, [rbp+arg_10]
0x1800195cb  mov     rdx, [rbp+arg_18]
0x1800195cf  mov     rax, [rcx]
0x1800195d2  mov     rax, [rax+20h]
0x1800195d6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800195db  test    eax, eax
0x1800195dd  jns     short loc_180019616
0x1800195df  cmp     eax, 80070005h
0x1800195e4  jnz     short loc_180019612
0x1800195e6  lea     rcx, aWas; "WAS"
0x1800195ed  call    ?StartIISService@@YAJPEBG@Z; StartIISService(ushort const *)
0x1800195f2  test    eax, eax
0x1800195f4  js      short loc_180019612
0x1800195f6  mov     rcx, [rbp+arg_8]
0x1800195fa  lea     r8, [rbp+arg_10]
0x1800195fe  mov     rdx, [rbp+arg_18]
0x180019602  mov     rax, [rcx]
0x180019605  mov     rax, [rax+20h]
0x180019609  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001960e  test    eax, eax
0x180019610  jns     short loc_180019616
0x180019612  xor     eax, eax
0x180019614  jmp     short loc_180019631
0x180019616  mov     rcx, [rbp+arg_10]
0x18001961a  mov     rax, [rcx]
0x18001961d  cmp     ebx, 1
0x180019620  jnz     short loc_180019628
0x180019622  mov     rax, [rax+28h]
0x180019626  jmp     short loc_18001962C
0x180019628  mov     rax, [rax+30h]
0x18001962c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180019631  mov     rcx, [rbp+arg_8]
0x180019635  xor     ebx, ebx
0x180019637  test    eax, eax
0x180019639  cmovns  ebx, eax
0x18001963c  test    rcx, rcx
0x18001963f  jz      short loc_180019655
0x180019641  mov     rax, [rcx]
0x180019644  mov     rax, [rax+10h]
0x180019648  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001964d  mov     [rbp+arg_8], 0
0x180019655  mov     rcx, [rbp+arg_10]
0x180019659  test    rcx, rcx
0x18001965c  jz      short loc_18001966A
0x18001965e  mov     rdx, [rcx]
0x180019661  mov     rax, [rdx+10h]
0x180019665  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001966a  mov     eax, ebx
0x18001966c  add     rsp, 30h
0x180019670  pop     rdi
0x180019671  pop     rbx
0x180019672  pop     rbp
0x180019673  retn
```
