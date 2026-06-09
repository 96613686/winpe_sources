# SITE_CUSTOM_PROVIDER::HandleSiteCommand(PROPERTY_ENTRY *)

- ea: `0x180015200`
- end: `0x1800153eb`
- name: `?HandleSiteCommand@SITE_CUSTOM_PROVIDER@@AEAAJPEAVPROPERTY_ENTRY@@@Z`
- size: `491`
- prototype: `__int64 __fastcall(SITE_CUSTOM_PROVIDER *__hidden this, struct PROPERTY_ENTRY *)`
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callers

- `0x180015880`

## callees

- `0x180015200`
- `0x1800271e4`
- `0x18002c010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180015258`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180015258`
- `iisutil!?QueryPtr@BUFFER@@QEBAPEAXXZ` at `0x18001526c`
- `iisutil!?QueryPtr@BUFFER@@QEBAPEAXXZ` at `0x18001526c`

## pseudocode

```c
__int64 __fastcall SITE_CUSTOM_PROVIDER::HandleSiteCommand(SITE_CUSTOM_PROVIDER *this, struct PROPERTY_ENTRY *a2)
{
  HRESULT started; // ebx
  _QWORD *Ptr; // rax
  BOOL v6; // edi
  _DWORD *v7; // rcx
  int v8; // eax
  __int64 v9; // rax
  __int64 (*v10)(void); // rax
  __int64 v11; // rax
  __int64 (*v12)(void); // rax
  __int64 result; // rax
  unsigned int v14; // [rsp+58h] [rbp+28h] BYREF
  __int64 *v15; // [rsp+60h] [rbp+30h] BYREF
  LPVOID ppv; // [rsp+68h] [rbp+38h] BYREF

  v15 = 0;
  v14 = 0;
  ppv = 0;
  if ( a2 )
  {
    started = CoCreateInstance(&CLSID_RSCA_W3SVC, 0, 0x15u, &IID_IRSCA_W3SVC, &ppv);
    if ( started >= 0 )
    {
      Ptr = BUFFER::QueryPtr((struct PROPERTY_ENTRY *)((char *)a2 + 16));
      v6 = 1;
      v7 = (_DWORD *)Ptr[3];
      if ( *v7 != 1 )
        v6 = *v7 == 4;
      started = (*(__int64 (__fastcall **)(_QWORD, const wchar_t *, BOOL, _QWORD))(**((_QWORD **)this + 3) + 136LL))(
                  *((_QWORD *)this + 3),
                  L"serverAutoStart",
                  v6,
                  0);
      if ( started >= 0 )
      {
        started = (*(__int64 (__fastcall **)(_QWORD, const wchar_t *, unsigned int *, _QWORD, _QWORD))(**((_QWORD **)this + 3) + 48LL))(
                    *((_QWORD *)this + 3),
                    L"id",
                    &v14,
                    0,
                    0);
        if ( started >= 0 )
        {
          started = (*(__int64 (__fastcall **)(LPVOID, _QWORD))(*(_QWORD *)ppv + 24LL))(ppv, 0);
          if ( started >= 0 )
          {
            v8 = (*(__int64 (__fastcall **)(LPVOID, _QWORD, __int64 **))(*(_QWORD *)ppv + 32LL))(ppv, v14, &v15);
            started = v8;
            if ( v8 >= 0
              || v8 == -2147024891
              && (started = StartIISService(L"W3SVC"), started >= 0)
              && (started = (*(__int64 (__fastcall **)(LPVOID, _QWORD, __int64 **))(*(_QWORD *)ppv + 32LL))(
                              ppv,
                              v14,
                              &v15),
                  started >= 0) )
            {
              v9 = *v15;
              v10 = v6 ? *(__int64 (**)(void))(v9 + 40) : *(__int64 (**)(void))(v9 + 48);
              started = v10();
              if ( started == -2147023834 )
              {
                started = StartIISService(L"W3SVC");
                if ( started >= 0 )
                {
                  v11 = *v15;
                  if ( v6 )
                    v12 = *(__int64 (**)(void))(v11 + 40);
                  else
                    v12 = *(__int64 (**)(void))(v11 + 48);
                  started = v12();
                }
              }
            }
          }
        }
      }
    }
    if ( v15 )
    {
      (*(void (__fastcall **)(__int64 *))(*v15 + 16))(v15);
      v15 = 0;
    }
    if ( ppv )
      (*(void (__fastcall **)(LPVOID))(*(_QWORD *)ppv + 16LL))(ppv);
  }
  else
  {
    started = -2147024809;
  }
  result = 0;
  if ( started >= 0 )
    return (unsigned int)started;
  return result;
}

```

## disassembly

```asm
0x180015200  mov     [rsp-18h+arg_0], rbx
0x180015205  push    rbp
0x180015206  push    rsi
0x180015207  push    rdi
0x180015208  mov     rbp, rsp
0x18001520b  sub     rsp, 30h
0x18001520f  mov     [rbp+arg_10], 0
0x180015217  mov     rdi, rdx
0x18001521a  mov     [rbp+arg_8], 0
0x180015221  mov     rsi, rcx
0x180015224  mov     [rbp+arg_18], 0
0x18001522c  test    rdx, rdx
0x18001522f  jnz     short loc_18001523B
0x180015231  mov     ebx, 80070057h
0x180015236  jmp     loc_1800153D7
0x18001523b  xor     edx, edx; pUnkOuter
0x18001523d  lea     rax, [rbp+arg_18]
0x180015241  lea     r9, IID_IRSCA_W3SVC; riid
0x180015248  mov     [rsp+30h+ppv], rax; ppv
0x18001524d  lea     rcx, CLSID_RSCA_W3SVC; rclsid
0x180015254  lea     r8d, [rdx+15h]; dwClsContext
0x180015258  call    cs:__imp_CoCreateInstance
0x18001525e  mov     ebx, eax
0x180015260  test    eax, eax
0x180015262  js      loc_1800153A5
0x180015268  lea     rcx, [rdi+10h]
0x18001526c  call    cs:__imp_?QueryPtr@BUFFER@@QEBAPEAXXZ; BUFFER::QueryPtr(void)
0x180015272  mov     edi, 1
0x180015277  mov     rcx, [rax+18h]
0x18001527b  cmp     [rcx], edi
0x18001527d  jz      short loc_180015286
0x18001527f  cmp     dword ptr [rcx], 4
0x180015282  jz      short loc_180015286
0x180015284  xor     edi, edi
0x180015286  mov     rcx, [rsi+18h]
0x18001528a  lea     rdx, aServerautostar; "serverAutoStart"
0x180015291  xor     r9d, r9d
0x180015294  mov     r8d, edi
0x180015297  mov     rax, [rcx]
0x18001529a  mov     rax, [rax+88h]
0x1800152a1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800152a6  mov     ebx, eax
0x1800152a8  test    eax, eax
0x1800152aa  js      loc_1800153A5
0x1800152b0  mov     rcx, [rsi+18h]
0x1800152b4  lea     r8, [rbp+arg_8]
0x1800152b8  xor     r9d, r9d
0x1800152bb  mov     [rsp+30h+ppv], 0
0x1800152c4  lea     rdx, aId; "id"
0x1800152cb  mov     rax, [rcx]
0x1800152ce  mov     rax, [rax+30h]
0x1800152d2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800152d7  mov     ebx, eax
0x1800152d9  test    eax, eax
0x1800152db  js      loc_1800153A5
0x1800152e1  mov     rcx, [rbp+arg_18]
0x1800152e5  xor     edx, edx
0x1800152e7  mov     rax, [rcx]
0x1800152ea  mov     rax, [rax+18h]
0x1800152ee  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800152f3  mov     ebx, eax
0x1800152f5  test    eax, eax
0x1800152f7  js      loc_1800153A5
0x1800152fd  mov     rcx, [rbp+arg_18]
0x180015301  lea     r8, [rbp+arg_10]
0x180015305  mov     edx, [rbp+arg_8]
0x180015308  mov     rax, [rcx]
0x18001530b  mov     rax, [rax+20h]
0x18001530f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015314  mov     ebx, eax
0x180015316  test    eax, eax
0x180015318  jns     short loc_180015354
0x18001531a  cmp     eax, 80070005h
0x18001531f  jnz     loc_1800153A5
0x180015325  lea     rcx, ServiceName; "W3SVC"
0x18001532c  call    ?StartIISService@@YAJPEBG@Z; StartIISService(ushort const *)
0x180015331  mov     ebx, eax
0x180015333  test    eax, eax
0x180015335  js      short loc_1800153A5
0x180015337  mov     rcx, [rbp+arg_18]
0x18001533b  lea     r8, [rbp+arg_10]
0x18001533f  mov     edx, [rbp+arg_8]
0x180015342  mov     rax, [rcx]
0x180015345  mov     rax, [rax+20h]
0x180015349  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001534e  mov     ebx, eax
0x180015350  test    eax, eax
0x180015352  js      short loc_1800153A5
0x180015354  mov     rcx, [rbp+arg_10]
0x180015358  mov     rax, [rcx]
0x18001535b  test    edi, edi
0x18001535d  jz      short loc_180015365
0x18001535f  mov     rax, [rax+28h]
0x180015363  jmp     short loc_180015369
0x180015365  mov     rax, [rax+30h]
0x180015369  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001536e  mov     ebx, eax
0x180015370  cmp     eax, 80070426h
0x180015375  jnz     short loc_1800153A5
0x180015377  lea     rcx, ServiceName; "W3SVC"
0x18001537e  call    ?StartIISService@@YAJPEBG@Z; StartIISService(ushort const *)
0x180015383  mov     ebx, eax
0x180015385  test    eax, eax
0x180015387  js      short loc_1800153A5
0x180015389  mov     rcx, [rbp+arg_10]
0x18001538d  mov     rax, [rcx]
0x180015390  test    edi, edi
0x180015392  jz      short loc_18001539A
0x180015394  mov     rax, [rax+28h]
0x180015398  jmp     short loc_18001539E
0x18001539a  mov     rax, [rax+30h]
0x18001539e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800153a3  mov     ebx, eax
0x1800153a5  mov     rcx, [rbp+arg_10]
0x1800153a9  test    rcx, rcx
0x1800153ac  jz      short loc_1800153C2
0x1800153ae  mov     rax, [rcx]
0x1800153b1  mov     rax, [rax+10h]
0x1800153b5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800153ba  mov     [rbp+arg_10], 0
0x1800153c2  mov     rcx, [rbp+arg_18]
0x1800153c6  test    rcx, rcx
0x1800153c9  jz      short loc_1800153D7
0x1800153cb  mov     rax, [rcx]
0x1800153ce  mov     rax, [rax+10h]
0x1800153d2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800153d7  xor     eax, eax
0x1800153d9  test    ebx, ebx
0x1800153db  cmovns  eax, ebx
0x1800153de  mov     rbx, [rsp+30h+arg_0]
0x1800153e3  add     rsp, 30h
0x1800153e7  pop     rdi
0x1800153e8  pop     rsi
0x1800153e9  pop     rbp
0x1800153ea  retn
```
