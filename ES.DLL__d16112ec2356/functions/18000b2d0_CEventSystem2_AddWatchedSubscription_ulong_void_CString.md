# CEventSystem2::AddWatchedSubscription(ulong,void *,CString &)

- ea: `0x18000b2d0`
- end: `0x18000b459`
- name: `?AddWatchedSubscription@CEventSystem2@@AEAA_NKPEAXAEAVCString@@@Z`
- size: `393`
- prototype: `bool(CEventSystem2 *__hidden this, unsigned int, void *, struct CString *)`
- caller_count: `1`
- callee_count: `4`
- tags: `service_task, broker_com_uri`

## callers

- `0x18000bf40`

## callees

- `0x18000b214`
- `0x18000b2d0`
- `0x18000b460`
- `0x180020350`

## import_xrefs

- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000b319`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000b416`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000b319`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000b416`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolWait` at `0x18000b406`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolWait` at `0x18000b406`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWait` at `0x18000b3b7`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWait` at `0x18000b3b7`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWait` at `0x18000b42e`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWait` at `0x18000b42e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18000b35f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18000b35f`

## pseudocode

```c
char __fastcall CEventSystem2::AddWatchedSubscription(
        CEventSystem2 *this,
        unsigned int a2,
        void *a3,
        const OLECHAR **a4)
{
  char *v4; // r15
  unsigned __int64 v5; // rsi
  __int64 v6; // rbx
  char v7; // di
  __int64 *i; // rbx
  __int64 v11; // rbx
  const OLECHAR *v12; // rax
  _DWORD *v14; // rax
  _DWORD *v15; // rbx
  PTP_WAIT ThreadpoolWait; // rax
  const OLECHAR *v17; // rax
  unsigned int v18; // edx
  struct _TP_WAIT *v19; // rcx
  const OLECHAR *v20; // [rsp+60h] [rbp+8h] BYREF

  v4 = (char *)this + 80;
  v5 = a2;
  v6 = *((_QWORD *)this + 10);
  v7 = 0;
  if ( v6 )
  {
    for ( i = *(__int64 **)(v6 + 8LL * ((a2 >> 4) % *((_DWORD *)this + 22))); i; i = (__int64 *)*i )
    {
      if ( *((_DWORD *)i + 3) == a2 )
      {
        v11 = i[2];
        CloseHandle(a3);
        v12 = *a4;
        if ( *((int *)*a4 - 3) < 0 )
          v12 = &dword_180053104;
        else
          _InterlockedIncrement((volatile signed __int32 *)v12 - 3);
        v20 = v12;
        if ( (int)CList<CString,CString>::AddTail(v11 + 24, &v20) < 0 )
          return v7;
        return 1;
      }
    }
  }
  v14 = CoTaskMemAlloc(0x48u);
  v15 = v14;
  if ( !v14 )
  {
    v15 = 0;
    goto LABEL_19;
  }
  v14[10] = 0;
  *((_QWORD *)v14 + 6) = 0;
  *((_QWORD *)v14 + 4) = 0;
  *((_QWORD *)v14 + 3) = 0;
  *((_QWORD *)v14 + 7) = 0;
  v14[16] = 10;
  *(_QWORD *)v14 = 0;
  *((_QWORD *)v14 + 1) = a3;
  ThreadpoolWait = CreateThreadpoolWait(CEventSystem2::SubscriberProcessTerminatedWaitCallback, (PVOID)v5, 0);
  *((_QWORD *)v15 + 2) = ThreadpoolWait;
  if ( !ThreadpoolWait )
    goto LABEL_19;
  v17 = *a4;
  if ( *((int *)*a4 - 3) < 0 )
    v17 = &dword_180053104;
  else
    _InterlockedIncrement((volatile signed __int32 *)v17 - 3);
  v20 = v17;
  if ( (int)CList<CString,CString>::AddTail(v15 + 6, &v20) < 0
    || (int)CMap<unsigned long,unsigned long,CEventSystem2::TransientSubscriberProcessData *,CEventSystem2::TransientSubscriberProcessData *>::SetAt(
              v4,
              (unsigned int)v5,
              v15) < 0 )
  {
LABEL_19:
    CloseHandle(a3);
    if ( v15 )
    {
      v19 = (struct _TP_WAIT *)*((_QWORD *)v15 + 2);
      if ( v19 )
        CloseThreadpoolWait(v19);
      CEventSystem2::TransientSubscriberProcessData::`scalar deleting destructor'(
        (CEventSystem2::TransientSubscriberProcessData *)v15,
        v18);
    }
    return v7;
  }
  SetThreadpoolWait(*((PTP_WAIT *)v15 + 2), *((HANDLE *)v15 + 1), 0);
  return 1;
}

```

## disassembly

```asm
0x18000b2d0  push    rbx
0x18000b2d2  push    rbp
0x18000b2d3  push    rsi
0x18000b2d4  push    rdi
0x18000b2d5  push    r14
0x18000b2d7  push    r15
0x18000b2d9  sub     rsp, 28h
0x18000b2dd  lea     r15, [rcx+50h]
0x18000b2e1  mov     esi, edx
0x18000b2e3  mov     rbx, [r15]
0x18000b2e6  xor     dil, dil
0x18000b2e9  mov     r14, r9
0x18000b2ec  mov     rbp, r8
0x18000b2ef  test    rbx, rbx
0x18000b2f2  jz      short loc_18000B35A
0x18000b2f4  xor     edx, edx
0x18000b2f6  mov     eax, esi
0x18000b2f8  shr     eax, 4
0x18000b2fb  div     dword ptr [r15+8]
0x18000b2ff  mov     rbx, [rbx+rdx*8]
0x18000b303  test    rbx, rbx
0x18000b306  jz      short loc_18000B35A
0x18000b308  cmp     [rbx+0Ch], esi
0x18000b30b  jz      short loc_18000B312
0x18000b30d  mov     rbx, [rbx]
0x18000b310  jmp     short loc_18000B303
0x18000b312  mov     rbx, [rbx+10h]
0x18000b316  mov     rcx, rbp; hObject
0x18000b319  call    cs:__imp_CloseHandle
0x18000b31f  mov     rax, [r14]
0x18000b322  lea     rcx, [rbx+18h]
0x18000b326  cmp     dword ptr [rax-0Ch], 0
0x18000b32a  jl      loc_18000B441
0x18000b330  lock inc dword ptr [rax-0Ch]
0x18000b334  lea     rdx, [rsp+58h+arg_0]
0x18000b339  mov     [rsp+58h+arg_0], rax
0x18000b33e  call    ?AddTail@?$CList@VCString@@V1@@@QEAAJVCString@@PEAPEAU__POSITION@@@Z; CList<CString,CString>::AddTail(CString,__POSITION * *)
0x18000b343  test    eax, eax
0x18000b345  js      short loc_18000B34A
0x18000b347  mov     dil, 1
0x18000b34a  mov     al, dil
0x18000b34d  add     rsp, 28h
0x18000b351  pop     r15
0x18000b353  pop     r14
0x18000b355  pop     rdi
0x18000b356  pop     rsi
0x18000b357  pop     rbp
0x18000b358  pop     rbx
0x18000b359  retn
0x18000b35a  mov     ecx, 48h ; 'H'; cb
0x18000b35f  call    cs:__imp_CoTaskMemAlloc
0x18000b365  mov     rbx, rax
0x18000b368  test    rax, rax
0x18000b36b  jz      loc_18000B411
0x18000b371  mov     dword ptr [rax+28h], 0
0x18000b378  lea     rcx, ?SubscriberProcessTerminatedWaitCallback@CEventSystem2@@CAXPEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_WAIT@@K@Z; pfnwa
0x18000b37f  mov     qword ptr [rax+30h], 0
0x18000b387  mov     rdx, rsi; pv
0x18000b38a  mov     qword ptr [rax+20h], 0
0x18000b392  xor     r8d, r8d; pcbe
0x18000b395  mov     qword ptr [rax+18h], 0
0x18000b39d  mov     qword ptr [rax+38h], 0
0x18000b3a5  mov     dword ptr [rax+40h], 0Ah
0x18000b3ac  mov     qword ptr [rax], 0
0x18000b3b3  mov     [rax+8], rbp
0x18000b3b7  call    cs:__imp_CreateThreadpoolWait
0x18000b3bd  mov     [rbx+10h], rax
0x18000b3c1  test    rax, rax
0x18000b3c4  jz      short loc_18000B413
0x18000b3c6  mov     rax, [r14]
0x18000b3c9  cmp     dword ptr [rax-0Ch], 0
0x18000b3cd  jl      short loc_18000B44D
0x18000b3cf  lock inc dword ptr [rax-0Ch]
0x18000b3d3  lea     rcx, [rbx+18h]
0x18000b3d7  mov     [rsp+58h+arg_0], rax
0x18000b3dc  lea     rdx, [rsp+58h+arg_0]
0x18000b3e1  call    ?AddTail@?$CList@VCString@@V1@@@QEAAJVCString@@PEAPEAU__POSITION@@@Z; CList<CString,CString>::AddTail(CString,__POSITION * *)
0x18000b3e6  test    eax, eax
0x18000b3e8  js      short loc_18000B413
0x18000b3ea  mov     r8, rbx
0x18000b3ed  mov     edx, esi
0x18000b3ef  mov     rcx, r15
0x18000b3f2  call    ?SetAt@?$CMap@KKPEAUTransientSubscriberProcessData@CEventSystem2@@PEAU12@@@QEAAJKPEAUTransientSubscriberProcessData@CEventSystem2@@@Z; CMap<ulong,ulong,CEventSystem2::TransientSubscriberProcessData *,CEventSystem2::TransientSubscriberProcessData *>::SetAt(ulong,CEventSystem2::TransientSubscriberProcessData *)
0x18000b3f7  test    eax, eax
0x18000b3f9  js      short loc_18000B413
0x18000b3fb  mov     rdx, [rbx+8]; h
0x18000b3ff  xor     r8d, r8d; pftTimeout
0x18000b402  mov     rcx, [rbx+10h]; pwa
0x18000b406  call    cs:__imp_SetThreadpoolWait
0x18000b40c  jmp     loc_18000B347
0x18000b411  xor     ebx, ebx
0x18000b413  mov     rcx, rbp; hObject
0x18000b416  call    cs:__imp_CloseHandle
0x18000b41c  test    rbx, rbx
0x18000b41f  jz      loc_18000B34A
0x18000b425  mov     rcx, [rbx+10h]; pwa
0x18000b429  test    rcx, rcx
0x18000b42c  jz      short loc_18000B434
0x18000b42e  call    cs:__imp_CloseThreadpoolWait
0x18000b434  mov     rcx, rbx; this
0x18000b437  call    ??_GTransientSubscriberProcessData@CEventSystem2@@QEAAPEAXI@Z; CEventSystem2::TransientSubscriberProcessData::`scalar deleting destructor'(uint)
0x18000b43c  jmp     loc_18000B34A
0x18000b441  mov     rax, cs:off_1800497D0
0x18000b448  jmp     loc_18000B334
0x18000b44d  mov     rax, cs:off_1800497D0
0x18000b454  jmp     loc_18000B3D3
```
