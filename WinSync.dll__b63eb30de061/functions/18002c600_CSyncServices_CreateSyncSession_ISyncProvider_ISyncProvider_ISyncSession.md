# CSyncServices::CreateSyncSession(ISyncProvider *,ISyncProvider *,ISyncSession * *)

- ea: `0x18002c600`
- end: `0x18002c7eb`
- name: `?CreateSyncSession@CSyncServices@@UEAAJPEAUISyncProvider@@0PEAPEAUISyncSession@@@Z`
- size: `491`
- prototype: `__int64 __fastcall(CSyncServices *this, struct ISyncProvider *, struct ISyncProvider *, struct ISyncSession **)`
- caller_count: `0`
- callee_count: `10`
- tags: `service_task`

## callees

- `0x18000a0f0`
- `0x18001a038`
- `0x18001ae20`
- `0x18001fd1c`
- `0x180020688`
- `0x18002c600`
- `0x18002d180`
- `0x18002dcac`
- `0x180093270`
- `0x180094010`

## string_xrefs

- `0x18002c64f`: `CSyncServices::CreateSyncSession`
- `0x18002c7af`: `CSyncServices::CreateSyncSession`

## pseudocode

```c
__int64 __fastcall CSyncServices::CreateSyncSession(
        CSyncServices *this,
        struct ISyncProvider *a2,
        struct ISyncProvider *a3,
        struct ISyncSession **a4)
{
  PVOID *v7; // rcx
  int Instance; // ebx
  struct ISyncProviderVtbl *lpVtbl; // rax
  HRESULT (__stdcall *GetIdParameters)(ISyncProvider *, ID_PARAMETERS *); // rax
  IdParameters *v11; // rax
  const struct _GUID *v12; // r9
  IdParameters *v13; // rdi
  _ID_PARAMETERS v15; // [rsp+30h] [rbp-50h] BYREF
  struct _ID_PARAMETERS v16; // [rsp+50h] [rbp-30h] BYREF

  v7 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_s(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      12,
      WPP_3949be9dc30c34dae78cb18c6e9e78ff_Traceguids,
      "CSyncServices::CreateSyncSession");
    v7 = (PVOID *)WPP_GLOBAL_Control;
  }
  Instance = -2147467261;
  if ( a2 && a3 && a4 )
  {
    lpVtbl = a2->lpVtbl;
    memset(&v15, 0, sizeof(v15));
    GetIdParameters = lpVtbl->GetIdParameters;
    memset(&v16, 0, sizeof(v16));
    Instance = ((__int64 (__fastcall *)(struct ISyncProvider *, _ID_PARAMETERS *))GetIdParameters)(a2, &v15);
    if ( Instance >= 0 )
    {
      Instance = ((__int64 (__fastcall *)(struct ISyncProvider *, struct _ID_PARAMETERS *))a3->lpVtbl->GetIdParameters)(
                   a3,
                   &v16);
      if ( Instance >= 0 )
      {
        Instance = -2147217408;
        if ( (unsigned int)IdParameters::EqualParameters(&v15, &v16) )
        {
          if ( (unsigned int)IdParameters::ValidParameters(&v15) )
          {
            Instance = -2147024882;
            v11 = (IdParameters *)SeAlloc(0x38u);
            v13 = v11;
            if ( v11 )
            {
              *(ID_PARAMETER_PAIR *)v11 = v15.replicaId;
              *((_QWORD *)v11 + 1) = 0;
              *((ID_PARAMETER_PAIR *)v11 + 2) = v15.itemId;
              *((_QWORD *)v11 + 3) = 0;
              *((ID_PARAMETER_PAIR *)v11 + 4) = v15.changeUnitId;
              *((_QWORD *)v11 + 5) = 0;
              *((_DWORD *)v11 + 12) = 1;
              *((_QWORD *)v11 + 1) = v11;
              *((_QWORD *)v11 + 3) = v11;
              *((_QWORD *)v11 + 5) = v11;
              Instance = CSyncSession_CreateInstance(v11, a2, a3, v12, (void **)a4);
              IdParameters::Release(v13);
            }
          }
        }
      }
    }
    v7 = (PVOID *)WPP_GLOBAL_Control;
  }
  if ( v7 != &WPP_GLOBAL_Control && (*((_BYTE *)v7 + 28) & 2) != 0 && *((_BYTE *)v7 + 25) >= 5u )
    WPP_SF_sD(
      (unsigned int)v7[2],
      13,
      (unsigned int)WPP_3949be9dc30c34dae78cb18c6e9e78ff_Traceguids,
      (unsigned int)"CSyncServices::CreateSyncSession",
      Instance);
  return (unsigned int)Instance;
}

```

## disassembly

```asm
0x18002c600  push    rbp
0x18002c602  push    rbx
0x18002c603  push    rsi
0x18002c604  push    rdi
0x18002c605  push    r13
0x18002c607  push    r14
0x18002c609  push    r15
0x18002c60b  mov     rbp, rsp
0x18002c60e  sub     rsp, 80h
0x18002c615  mov     rax, cs:__security_cookie
0x18002c61c  xor     rax, rsp
0x18002c61f  mov     [rbp+var_10], rax
0x18002c623  mov     r15, r9
0x18002c626  mov     rsi, r8
0x18002c629  mov     r14, rdx
0x18002c62c  mov     rcx, cs:WPP_GLOBAL_Control
0x18002c633  lea     r13, WPP_GLOBAL_Control
0x18002c63a  cmp     rcx, r13
0x18002c63d  jz      short loc_18002C66E
0x18002c63f  test    byte ptr [rcx+1Ch], 2
0x18002c643  jz      short loc_18002C66E
0x18002c645  cmp     byte ptr [rcx+19h], 5
0x18002c649  jb      short loc_18002C66E
0x18002c64b  mov     rcx, [rcx+10h]
0x18002c64f  lea     r9, aCsyncservicesC_8; "CSyncServices::CreateSyncSession"
0x18002c656  mov     edx, 0Ch
0x18002c65b  lea     r8, WPP_3949be9dc30c34dae78cb18c6e9e78ff_Traceguids
0x18002c662  call    WPP_SF_s
0x18002c667  mov     rcx, cs:WPP_GLOBAL_Control
0x18002c66e  mov     ebx, 80004003h
0x18002c673  test    r14, r14
0x18002c676  jz      loc_18002C79A
0x18002c67c  test    rsi, rsi
0x18002c67f  jz      loc_18002C79A
0x18002c685  test    r15, r15
0x18002c688  jz      loc_18002C79A
0x18002c68e  xor     eax, eax
0x18002c690  lea     rdx, [rbp+var_50]
0x18002c694  mov     rax, [r14]
0x18002c697  xorps   xmm0, xmm0
0x18002c69a  xorps   xmm1, xmm1
0x18002c69d  mov     rcx, r14
0x18002c6a0  movups  xmmword ptr [rbp+var_50.dwSize], xmm0
0x18002c6a4  mov     rax, [rax+18h]
0x18002c6a8  movups  xmmword ptr [rbp+var_30.dwSize], xmm1
0x18002c6ac  movups  xmmword ptr [rbp+var_50.itemId.fIsVariable], xmm0
0x18002c6b0  movups  xmmword ptr [rbp+var_30.itemId.fIsVariable], xmm1
0x18002c6b4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002c6b9  mov     ebx, eax
0x18002c6bb  test    eax, eax
0x18002c6bd  js      loc_18002C793
0x18002c6c3  mov     rax, [rsi]
0x18002c6c6  lea     rdx, [rbp+var_30]
0x18002c6ca  mov     rcx, rsi
0x18002c6cd  mov     rax, [rax+18h]
0x18002c6d1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002c6d6  mov     ebx, eax
0x18002c6d8  test    eax, eax
0x18002c6da  js      loc_18002C793
0x18002c6e0  lea     rdx, [rbp+var_30]; struct _ID_PARAMETERS *
0x18002c6e4  mov     ebx, 80041000h
0x18002c6e9  lea     rcx, [rbp+var_50]; struct _ID_PARAMETERS *
0x18002c6ed  call    ?EqualParameters@IdParameters@@SAHPEBU_ID_PARAMETERS@@0@Z; IdParameters::EqualParameters(_ID_PARAMETERS const *,_ID_PARAMETERS const *)
0x18002c6f2  test    eax, eax
0x18002c6f4  jz      loc_18002C793
0x18002c6fa  lea     rcx, [rbp+var_50]; struct _ID_PARAMETERS *
0x18002c6fe  call    ?ValidParameters@IdParameters@@SAHPEBU_ID_PARAMETERS@@@Z; IdParameters::ValidParameters(_ID_PARAMETERS const *)
0x18002c703  test    eax, eax
0x18002c705  jz      loc_18002C793
0x18002c70b  mov     ecx, 38h ; '8'; unsigned __int64
0x18002c710  mov     ebx, 8007000Eh
0x18002c715  call    ?SeAlloc@@YAPEAX_K@Z; SeAlloc(unsigned __int64)
0x18002c71a  mov     rdi, rax
0x18002c71d  test    rax, rax
0x18002c720  jz      short loc_18002C793
0x18002c722  mov     ecx, [rbp+var_50.replicaId.fIsVariable]
0x18002c725  mov     r8, rsi; struct ISyncProvider *
0x18002c728  mov     [rax], ecx
0x18002c72a  mov     rdx, r14; struct ISyncProvider *
0x18002c72d  movzx   ecx, [rbp+var_50.replicaId.cbIdSize]
0x18002c731  mov     [rax+4], cx
0x18002c735  mov     qword ptr [rax+8], 0
0x18002c73d  mov     ecx, [rbp+var_50.itemId.fIsVariable]
0x18002c740  mov     [rax+10h], ecx
0x18002c743  movzx   ecx, [rbp+var_50.itemId.cbIdSize]
0x18002c747  mov     [rax+14h], cx
0x18002c74b  mov     rcx, rdi; struct IdParameters *
0x18002c74e  mov     qword ptr [rax+18h], 0
0x18002c756  mov     eax, [rbp+var_50.changeUnitId.fIsVariable]
0x18002c759  mov     [rdi+20h], eax
0x18002c75c  movzx   eax, [rbp+var_50.changeUnitId.cbIdSize]
0x18002c760  mov     [rdi+24h], ax
0x18002c764  mov     qword ptr [rdi+28h], 0
0x18002c76c  mov     dword ptr [rdi+30h], 1
0x18002c773  mov     [rdi+8], rdi
0x18002c777  mov     [rdi+18h], rdi
0x18002c77b  mov     [rdi+28h], rdi
0x18002c77f  mov     [rsp+80h+var_60], r15; void **
0x18002c784  call    ?CSyncSession_CreateInstance@@YAJPEAVIdParameters@@PEAUISyncProvider@@1AEBU_GUID@@PEAPEAX@Z; CSyncSession_CreateInstance(IdParameters *,ISyncProvider *,ISyncProvider *,_GUID const &,void * *)
0x18002c789  mov     rcx, rdi; this
0x18002c78c  mov     ebx, eax
0x18002c78e  call    ?Release@IdParameters@@QEAAKXZ; IdParameters::Release(void)
0x18002c793  mov     rcx, cs:WPP_GLOBAL_Control
0x18002c79a  cmp     rcx, r13
0x18002c79d  jz      short loc_18002C7CB
0x18002c79f  test    byte ptr [rcx+1Ch], 2
0x18002c7a3  jz      short loc_18002C7CB
0x18002c7a5  cmp     byte ptr [rcx+19h], 5
0x18002c7a9  jb      short loc_18002C7CB
0x18002c7ab  mov     rcx, [rcx+10h]
0x18002c7af  lea     r9, aCsyncservicesC_8; "CSyncServices::CreateSyncSession"
0x18002c7b6  mov     edx, 0Dh
0x18002c7bb  mov     dword ptr [rsp+80h+var_60], ebx
0x18002c7bf  lea     r8, WPP_3949be9dc30c34dae78cb18c6e9e78ff_Traceguids
0x18002c7c6  call    WPP_SF_sD
0x18002c7cb  mov     eax, ebx
0x18002c7cd  mov     rcx, [rbp+var_10]
0x18002c7d1  xor     rcx, rsp; StackCookie
0x18002c7d4  call    __security_check_cookie
0x18002c7d9  add     rsp, 80h
0x18002c7e0  pop     r15
0x18002c7e2  pop     r14
0x18002c7e4  pop     r13
0x18002c7e6  pop     rdi
0x18002c7e7  pop     rsi
0x18002c7e8  pop     rbx
0x18002c7e9  pop     rbp
0x18002c7ea  retn
```
