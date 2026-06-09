# CAppContainerCF::CreateConnectedInstance(CServerContext *,ushort const *,void *,void *,int,void * *)

- ea: `0x18001c84c`
- end: `0x18001ca8e`
- name: `?CreateConnectedInstance@CAppContainerCF@@QEAAJPEAVCServerContext@@PEBGPEAX2HPEAPEAX@Z`
- size: `578`
- prototype: `__int64 __fastcall(CAppContainerCF *this, struct CServerContext *, const unsigned __int16 *, void *, void *, int, void **)`
- caller_count: `1`
- callee_count: `7`
- tags: `broker_com_uri`

## callers

- `0x18001e2ec`

## callees

- `0x18001b1a0`
- `0x18001c258`
- `0x18001c84c`
- `0x1800245f0`
- `0x1800247a8`
- `0x180024920`
- `0x18002c010`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18001c90e`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18001c9b3`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18001c90e`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18001c9b3`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001c8f5`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001ca51`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001c8f5`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001ca51`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001c8a1`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001ca16`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001c8a1`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001ca16`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x18001c894`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x18001c894`

## pseudocode

```c
__int64 __fastcall CAppContainerCF::CreateConnectedInstance(
        CAppContainerCF *this,
        struct CServerContext *a2,
        const unsigned __int16 *a3,
        void *a4,
        void *a5,
        int a6,
        void **a7)
{
  void **v8; // r15
  CBindingList *v10; // rcx
  struct CBinding *v11; // rax
  int v12; // ebx
  struct CBinding *v13; // rdi
  CAppContainer *v15; // rax
  struct CServerContext *v16; // rdx
  CAppContainer *v17; // rax
  CAppContainer *v18; // rdi
  int v19; // edi
  CBinding *v20; // rax
  struct CServerContext *v21; // rdx
  CBinding *v22; // rax
  struct CBinding *v23; // rbx
  struct IClassAccess *v24; // rcx
  CBindingList *v25; // rcx
  struct CBinding *v26; // rax
  struct _FILETIME SystemTimeAsFileTime; // [rsp+40h] [rbp-10h] BYREF
  struct IClassAccess *v28; // [rsp+80h] [rbp+30h] BYREF
  int v29; // [rsp+88h] [rbp+38h] BYREF
  int v30; // [rsp+8Ch] [rbp+3Ch]

  v30 = HIDWORD(a2);
  v8 = a7;
  v29 = 0;
  SystemTimeAsFileTime = 0;
  v28 = 0;
  if ( a6 )
  {
    GetSystemTimeAsFileTime(&SystemTimeAsFileTime);
    EnterCriticalSection(&stru_180037510);
    v11 = CBindingList::Find(v10, 0, &SystemTimeAsFileTime, a3, a4);
    v12 = 0;
    v13 = v11;
    if ( v11 )
    {
      v12 = *((_DWORD *)v11 + 6);
      if ( v12 >= 0 )
        v12 = (***((__int64 (__fastcall ****)(_QWORD, GUID *, void **))v11 + 2))(
                *((_QWORD *)v11 + 2),
                &IID_IClassAccess,
                v8);
      v29 = v12;
    }
    LeaveCriticalSection(&stru_180037510);
    if ( v13 )
      return (unsigned int)v12;
  }
  v15 = (CAppContainer *)LocalAlloc(0, 0x4A0u);
  if ( v15 )
  {
    v17 = CAppContainer::CAppContainer(v15, v16, a3, a5, &v29);
    v18 = v17;
    if ( v17 )
    {
      v12 = v29;
      if ( v29 < 0 )
      {
        if ( gDebug )
          _DebugMsg(2, 0xC85u, a3, (unsigned int)v29);
      }
      else
      {
        v12 = (**(__int64 (__fastcall ***)(CAppContainer *, GUID *, struct IClassAccess **))v17)(
                v17,
                &IID_IClassAccess,
                &v28);
      }
      (*(void (__fastcall **)(CAppContainer *))(*(_QWORD *)v18 + 16LL))(v18);
      if ( a6 && (!v12 || v12 == -2147221143) )
      {
        v19 = -2147024882;
        a6 = -2147024882;
        v20 = (CBinding *)LocalAlloc(0, 0x40u);
        if ( v20 )
        {
          v22 = CBinding::CBinding(v20, v21, a3, a4, v28, v12, &a6);
          v19 = a6;
          v23 = v22;
        }
        else
        {
          v23 = 0;
        }
        if ( v19 >= 0 )
        {
          EnterCriticalSection(&stru_180037510);
          v26 = CBindingList::AddBinding(v25, &SystemTimeAsFileTime, v23);
          v12 = *((_DWORD *)v26 + 6);
          if ( v12 >= 0 )
            v12 = (***((__int64 (__fastcall ****)(_QWORD, GUID *, void **))v26 + 2))(
                    *((_QWORD *)v26 + 2),
                    &IID_IClassAccess,
                    v8);
          LeaveCriticalSection(&stru_180037510);
          goto LABEL_27;
        }
        v12 = v19;
      }
      if ( v12 >= 0 )
      {
        (*(void (__fastcall **)(struct IClassAccess *))(*(_QWORD *)v28 + 8LL))(v28);
        v24 = v28;
        *v8 = v28;
        goto LABEL_28;
      }
LABEL_27:
      v24 = v28;
LABEL_28:
      if ( v24 )
        (*(void (__fastcall **)(struct IClassAccess *))(*(_QWORD *)v24 + 16LL))(v24);
      return (unsigned int)v12;
    }
  }
  return 2147942414LL;
}

```

## disassembly

```asm
0x18001c84c  mov     [rsp-28h+arg_10], rbx
0x18001c851  mov     qword ptr [rsp-28h+arg_8], rdx
0x18001c856  mov     [rsp-28h+arg_0], rcx
0x18001c85b  push    rbp
0x18001c85c  push    rsi
0x18001c85d  push    rdi
0x18001c85e  push    r12
0x18001c860  push    r15
0x18001c862  mov     rbp, rsp
0x18001c865  sub     rsp, 50h
0x18001c869  cmp     [rbp+arg_28], 0
0x18001c86d  mov     r12, r9
0x18001c870  mov     r15, [rbp+arg_30]
0x18001c874  mov     rsi, r8
0x18001c877  mov     [rbp+arg_8], 0
0x18001c87e  mov     qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime], 0
0x18001c886  mov     [rbp+arg_0], 0
0x18001c88e  jz      short loc_18001C907
0x18001c890  lea     rcx, [rbp+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x18001c894  call    cs:__imp_GetSystemTimeAsFileTime
0x18001c89a  lea     rcx, stru_180037510; lpCriticalSection
0x18001c8a1  call    cs:__imp_EnterCriticalSection
0x18001c8a7  mov     r9, rsi; unsigned __int16 *
0x18001c8aa  mov     [rsp+50h+var_30], r12; void *
0x18001c8af  lea     r8, [rbp+SystemTimeAsFileTime]; struct _FILETIME *
0x18001c8b3  xor     edx, edx; struct CServerContext *
0x18001c8b5  call    ?Find@CBindingList@@QEAAPEAVCBinding@@PEAVCServerContext@@PEAU_FILETIME@@PEBGPEAX@Z; CBindingList::Find(CServerContext *,_FILETIME *,ushort const *,void *)
0x18001c8ba  xor     ebx, ebx
0x18001c8bc  mov     rdi, rax
0x18001c8bf  test    rax, rax
0x18001c8c2  jz      short loc_18001C8EE
0x18001c8c4  mov     ebx, [rax+18h]
0x18001c8c7  test    ebx, ebx
0x18001c8c9  jns     short loc_18001C8D0
0x18001c8cb  mov     [rbp+arg_8], ebx
0x18001c8ce  jmp     short loc_18001C8EE
0x18001c8d0  mov     rcx, [rax+10h]
0x18001c8d4  lea     rdx, IID_IClassAccess
0x18001c8db  mov     r8, r15
0x18001c8de  mov     rax, [rcx]
0x18001c8e1  mov     rax, [rax]
0x18001c8e4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001c8e9  mov     ebx, eax
0x18001c8eb  mov     [rbp+arg_8], eax
0x18001c8ee  lea     rcx, stru_180037510; lpCriticalSection
0x18001c8f5  call    cs:__imp_LeaveCriticalSection
0x18001c8fb  test    rdi, rdi
0x18001c8fe  jz      short loc_18001C907
0x18001c900  mov     eax, ebx
0x18001c902  jmp     loc_18001CA7A
0x18001c907  mov     edx, 4A0h; uBytes
0x18001c90c  xor     ecx, ecx; uFlags
0x18001c90e  call    cs:__imp_LocalAlloc
0x18001c914  test    rax, rax
0x18001c917  jz      loc_18001CA75
0x18001c91d  mov     r9, [rbp+arg_20]; void *
0x18001c921  lea     rcx, [rbp+arg_8]
0x18001c925  mov     [rsp+50h+var_30], rcx; int *
0x18001c92a  mov     r8, rsi; unsigned __int16 *
0x18001c92d  mov     rcx, rax; this
0x18001c930  call    ??0CAppContainer@@QEAA@PEAVCServerContext@@PEBGPEAXPEAJ@Z; CAppContainer::CAppContainer(CServerContext *,ushort const *,void *,long *)
0x18001c935  mov     rdi, rax
0x18001c938  test    rax, rax
0x18001c93b  jz      loc_18001CA75
0x18001c941  mov     ebx, [rbp+arg_8]
0x18001c944  test    ebx, ebx
0x18001c946  js      short loc_18001C965
0x18001c948  mov     rcx, [rax]
0x18001c94b  lea     r8, [rbp+arg_0]
0x18001c94f  lea     rdx, IID_IClassAccess
0x18001c956  mov     rax, [rcx]
0x18001c959  mov     rcx, rdi
0x18001c95c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001c961  mov     ebx, eax
0x18001c963  jmp     short loc_18001C983
0x18001c965  cmp     cs:?gDebug@@3KA, 0; ulong gDebug
0x18001c96c  jz      short loc_18001C983
0x18001c96e  mov     r9d, ebx
0x18001c971  mov     r8, rsi
0x18001c974  mov     edx, 0C85h; unsigned int
0x18001c979  mov     ecx, 2; unsigned int
0x18001c97e  call    ?_DebugMsg@@YAXKKZZ; _DebugMsg(ulong,ulong,...)
0x18001c983  mov     rax, [rdi]
0x18001c986  mov     rcx, rdi
0x18001c989  mov     rax, [rax+10h]
0x18001c98d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001c992  cmp     [rbp+arg_28], 0
0x18001c996  jz      short loc_18001C9F2
0x18001c998  test    ebx, ebx
0x18001c99a  jz      short loc_18001C9A4
0x18001c99c  cmp     ebx, 80040169h
0x18001c9a2  jnz     short loc_18001C9F2
0x18001c9a4  mov     edi, 8007000Eh
0x18001c9a9  mov     edx, 40h ; '@'; uBytes
0x18001c9ae  xor     ecx, ecx; uFlags
0x18001c9b0  mov     [rbp+arg_28], edi
0x18001c9b3  call    cs:__imp_LocalAlloc
0x18001c9b9  test    rax, rax
0x18001c9bc  jz      short loc_18001C9EA
0x18001c9be  lea     rcx, [rbp+arg_28]
0x18001c9c2  mov     r9, r12; void *
0x18001c9c5  mov     [rsp+50h+var_20], rcx; int *
0x18001c9ca  mov     r8, rsi; unsigned __int16 *
0x18001c9cd  mov     rcx, [rbp+arg_0]
0x18001c9d1  mov     [rsp+50h+var_28], ebx; int
0x18001c9d5  mov     [rsp+50h+var_30], rcx; struct IClassAccess *
0x18001c9da  mov     rcx, rax; this
0x18001c9dd  call    ??0CBinding@@QEAA@PEAVCServerContext@@PEBGPEAXPEAUIClassAccess@@JPEAJ@Z; CBinding::CBinding(CServerContext *,ushort const *,void *,IClassAccess *,long,long *)
0x18001c9e2  mov     edi, [rbp+arg_28]
0x18001c9e5  mov     rbx, rax
0x18001c9e8  jmp     short loc_18001C9EC
0x18001c9ea  xor     ebx, ebx
0x18001c9ec  test    edi, edi
0x18001c9ee  jns     short loc_18001CA0F
0x18001c9f0  mov     ebx, edi
0x18001c9f2  test    ebx, ebx
0x18001c9f4  js      short loc_18001CA57
0x18001c9f6  mov     rcx, [rbp+arg_0]
0x18001c9fa  mov     rax, [rcx]
0x18001c9fd  mov     rax, [rax+8]
0x18001ca01  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001ca06  mov     rcx, [rbp+arg_0]
0x18001ca0a  mov     [r15], rcx
0x18001ca0d  jmp     short loc_18001CA5B
0x18001ca0f  lea     rcx, stru_180037510; lpCriticalSection
0x18001ca16  call    cs:__imp_EnterCriticalSection
0x18001ca1c  mov     r8, rbx; struct CBinding *
0x18001ca1f  lea     rdx, [rbp+SystemTimeAsFileTime]; struct _FILETIME *
0x18001ca23  call    ?AddBinding@CBindingList@@QEAAPEAVCBinding@@PEAU_FILETIME@@PEAV2@@Z; CBindingList::AddBinding(_FILETIME *,CBinding *)
0x18001ca28  mov     ebx, [rax+18h]
0x18001ca2b  test    ebx, ebx
0x18001ca2d  js      short loc_18001CA4A
0x18001ca2f  mov     rcx, [rax+10h]
0x18001ca33  lea     rdx, IID_IClassAccess
0x18001ca3a  mov     r8, r15
0x18001ca3d  mov     rax, [rcx]
0x18001ca40  mov     rax, [rax]
0x18001ca43  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001ca48  mov     ebx, eax
0x18001ca4a  lea     rcx, stru_180037510; lpCriticalSection
0x18001ca51  call    cs:__imp_LeaveCriticalSection
0x18001ca57  mov     rcx, [rbp+arg_0]
0x18001ca5b  test    rcx, rcx
0x18001ca5e  jz      loc_18001C900
0x18001ca64  mov     rax, [rcx]
0x18001ca67  mov     rax, [rax+10h]
0x18001ca6b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001ca70  jmp     loc_18001C900
0x18001ca75  mov     eax, 8007000Eh
0x18001ca7a  mov     rbx, [rsp+50h+arg_10]
0x18001ca82  add     rsp, 50h
0x18001ca86  pop     r15
0x18001ca88  pop     r12
0x18001ca8a  pop     rdi
0x18001ca8b  pop     rsi
0x18001ca8c  pop     rbp
0x18001ca8d  retn
```
