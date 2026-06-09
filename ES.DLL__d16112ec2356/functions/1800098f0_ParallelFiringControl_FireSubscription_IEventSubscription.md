# ParallelFiringControl::FireSubscription(IEventSubscription *)

- ea: `0x1800098f0`
- end: `0x180009bea`
- name: `?FireSubscription@ParallelFiringControl@@UEAAJPEAUIEventSubscription@@@Z`
- size: `762`
- prototype: `__int64 __fastcall(ParallelFiringControl *__hidden this, struct IEventSubscription *)`
- caller_count: `0`
- callee_count: `10`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callees

- `0x180003d54`
- `0x180008938`
- `0x180009034`
- `0x18000985c`
- `0x1800098f0`
- `0x180009bf0`
- `0x180009e8c`
- `0x1800204d0`
- `0x18003ecb0`
- `0x180046010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ResetEvent` at `0x180009a8f`
- `api-ms-win-core-synch-l1-1-0!ResetEvent` at `0x180009a8f`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180009b60`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180009b60`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x1800099b2`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x1800099b2`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x1800099c9`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x1800099c9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800099d3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800099d3`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180009b9e`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180009b9e`
- `OLEAUT32!__imp_SysFreeString` at `0x180009af5`
- `OLEAUT32!__imp_SysFreeString` at `0x180009af5`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180009a0e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180009a0e`

## string_xrefs

- `0x180009950`: `com\complus\src\events\tier1\agent.cpp`
- `0x180009b43`: `com\complus\src\events\tier1\agent.cpp`
- `0x180009b83`: `com\complus\src\events\tier1\agent.cpp`
- `0x180009b77`: `CreateEvent`

## pseudocode

```c
__int64 __fastcall ParallelFiringControl::FireSubscription(ParallelFiringControl *this, struct IEventSubscription *a2)
{
  HANDLE CurrentThread; // rax
  __int64 result; // rax
  ParallelFiringCallback *v6; // rax
  ParallelFiringCallback *v7; // rdi
  __int64 v8; // rax
  unsigned int v9; // edx
  int v10; // eax
  HANDLE EventW; // rax
  __int64 *v12; // rcx
  int v13; // [rsp+40h] [rbp-28h]
  unsigned int v14; // [rsp+40h] [rbp-28h]
  int v15; // [rsp+40h] [rbp-28h]
  void *TokenHandle; // [rsp+48h] [rbp-20h] BYREF
  BSTR bstrString[3]; // [rsp+50h] [rbp-18h] BYREF
  int v18; // [rsp+80h] [rbp+18h] BYREF
  struct IEventSubscription *v19; // [rsp+88h] [rbp+20h] BYREF

  v18 = 0;
  TokenHandle = 0;
  v13 = ((__int64 (__fastcall *)(struct IEventSubscription *, int *))a2->lpVtbl->get_Enabled)(a2, &v18);
  if ( v13 < 0 )
    InternalError_HR(L"com\\complus\\src\\events\\tier1\\agent.cpp", 0xFE2u, 0x12u, v13);
  if ( !v18 )
    return 1;
  v19 = 0;
  ((void (__fastcall *)(struct IEventSubscription *, GUID *, struct IEventSubscription **))a2->lpVtbl->QueryInterface)(
    a2,
    &IID_IEventSubscription2,
    &v19);
  if ( v19 )
  {
    bstrString[0] = 0;
    ((void (__fastcall *)(struct IEventSubscription *, BSTR *))v19->lpVtbl[1].QueryInterface)(v19, bstrString);
    ((void (__fastcall *)(struct IEventSubscription *))v19->lpVtbl->Release)(v19);
    if ( bstrString[0] )
    {
      v15 = FiringControl::FilterUsingCriteria(this, bstrString[0], v19);
      SysFreeString(bstrString[0]);
      if ( v15 )
        return 1;
    }
  }
  if ( !*((_QWORD *)this + 8) )
  {
    EventW = CreateEventW(0, 1, 1, 0);
    *((_QWORD *)this + 8) = EventW;
    if ( !EventW )
      InternalError_Win32(L"com\\complus\\src\\events\\tier1\\agent.cpp", 0xFFEu, 0x12u, L"CreateEvent");
  }
  ++*((_DWORD *)this + 12);
  CurrentThread = GetCurrentThread();
  if ( !OpenThreadToken(CurrentThread, 4u, 1, &TokenHandle) )
  {
    LODWORD(result) = GetLastError();
    if ( (int)result > 0 )
      LODWORD(result) = (unsigned __int16)result | 0x80070000;
    if ( (_DWORD)result != -2147023888 )
      return (unsigned int)result;
    TokenHandle = 0;
  }
  v6 = (ParallelFiringCallback *)CoTaskMemAlloc(0x88u);
  if ( v6 )
    v7 = ParallelFiringCallback::ParallelFiringCallback(
           v6,
           this,
           a2,
           *((struct ICallFrame **)this + 5),
           (int *)this + 13,
           (int *)this + 14,
           *((void **)this + 8),
           TokenHandle);
  else
    v7 = 0;
  if ( !v7 )
  {
    if ( TokenHandle )
      CloseHandle(TokenHandle);
    InternalError(L"com\\complus\\src\\events\\tier1\\agent.cpp", 0x1023u, 0xC0001204, 0x12u);
  }
  v8 = CList<ParallelFiringCallback *,ParallelFiringCallback *>::NewNode((char *)this + 72, *((_QWORD *)this + 10));
  if ( v8 )
  {
    *(_QWORD *)(v8 + 16) = v7;
    v12 = (__int64 *)*((_QWORD *)this + 10);
    if ( v12 )
      *v12 = v8;
    else
      *((_QWORD *)this + 9) = v8;
    *((_QWORD *)this + 10) = v8;
    v10 = 0;
  }
  else
  {
    v10 = -2147024882;
  }
  v14 = v10;
  if ( v10 < 0 )
  {
    if ( v7 )
      ParallelFiringCallback::`scalar deleting destructor'(v7, v9);
  }
  else
  {
    ResetEvent(*((HANDLE *)this + 8));
    ++*((_DWORD *)this + 14);
  }
  return v14;
}

```

## disassembly

```asm
0x1800098f0  mov     r11, rsp
0x1800098f3  mov     [r11+8], rbx
0x1800098f7  mov     [r11+10h], rsi
0x1800098fb  push    rdi
0x1800098fc  sub     rsp, 60h
0x180009900  mov     rdi, rdx
0x180009903  mov     rbx, rcx
0x180009906  mov     [rsp+68h+var_28], 0
0x18000990e  mov     dword ptr [r11+18h], 0
0x180009916  mov     qword ptr [r11-20h], 0
0x18000991e  mov     rax, [rdx]
0x180009921  lea     rdx, [r11+18h]
0x180009925  mov     rcx, rdi
0x180009928  mov     rax, [rax+0C8h]
0x18000992f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009934  mov     [rsp+68h+var_28], eax
0x180009938  mov     eax, [rsp+68h+var_28]
0x18000993c  test    eax, eax
0x18000993e  jns     short loc_18000995C
0x180009940  mov     r8d, 12h; unsigned __int16
0x180009946  mov     r9d, [rsp+68h+var_28]; int
0x18000994b  mov     edx, 0FE2h; unsigned int
0x180009950  lea     rcx, aComComplusSrcE_10; "com\\complus\\src\\events\\tier1\\agent"...
0x180009957  call    ?InternalError_HR@@YA_NPEBGKGJ@Z; InternalError_HR(ushort const *,ulong,ushort,long)
0x18000995c  cmp     [rsp+68h+arg_10], 0
0x180009964  jz      loc_180009B18
0x18000996a  mov     [rsp+68h+arg_18], 0
0x180009976  mov     rax, [rdi]
0x180009979  lea     r8, [rsp+68h+arg_18]
0x180009981  lea     rdx, IID_IEventSubscription2
0x180009988  mov     rcx, rdi
0x18000998b  mov     rax, [rax]
0x18000998e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009993  mov     rcx, [rsp+68h+arg_18]
0x18000999b  test    rcx, rcx
0x18000999e  jnz     loc_180009A9D
0x1800099a4  cmp     qword ptr [rbx+40h], 0
0x1800099a9  jz      loc_180009B54
0x1800099af  inc     dword ptr [rbx+30h]
0x1800099b2  call    cs:__imp_GetCurrentThread
0x1800099b8  mov     rcx, rax; ThreadHandle
0x1800099bb  lea     r9, [rsp+68h+TokenHandle]; TokenHandle
0x1800099c0  mov     edx, 4; DesiredAccess
0x1800099c5  lea     r8d, [rdx-3]; OpenAsSelf
0x1800099c9  call    cs:__imp_OpenThreadToken
0x1800099cf  test    eax, eax
0x1800099d1  jnz     short loc_180009A09
0x1800099d3  call    cs:__imp_GetLastError
0x1800099d9  test    eax, eax
0x1800099db  jle     short loc_1800099E5
0x1800099dd  movzx   eax, ax
0x1800099e0  or      eax, 80070000h
0x1800099e5  mov     [rsp+68h+var_28], eax
0x1800099e9  mov     eax, [rsp+68h+var_28]
0x1800099ed  cmp     eax, 800703F0h
0x1800099f2  jnz     loc_180009B22
0x1800099f8  mov     [rsp+68h+var_28], 0
0x180009a00  mov     [rsp+68h+TokenHandle], 0
0x180009a09  mov     ecx, 88h; cb
0x180009a0e  call    cs:__imp_CoTaskMemAlloc
0x180009a14  test    rax, rax
0x180009a17  jz      loc_180009B11
0x180009a1d  lea     rdx, [rbx+38h]
0x180009a21  lea     r8, [rbx+34h]
0x180009a25  mov     rcx, [rsp+68h+TokenHandle]
0x180009a2a  mov     [rsp+68h+var_30], rcx; void *
0x180009a2f  mov     rcx, [rbx+40h]
0x180009a33  mov     [rsp+68h+var_38], rcx; void *
0x180009a38  mov     [rsp+68h+var_40], rdx; int *
0x180009a3d  mov     [rsp+68h+var_48], r8; int *
0x180009a42  mov     r9, [rbx+28h]; struct ICallFrame *
0x180009a46  mov     r8, rdi; struct IEventSubscription *
0x180009a49  mov     rdx, rbx; struct ParallelFiringControl *
0x180009a4c  mov     rcx, rax; this
0x180009a4f  call    ??0ParallelFiringCallback@@QEAA@AEAVParallelFiringControl@@PEAUIEventSubscription@@PEAUICallFrame@@PEAJ3PEAX4@Z; ParallelFiringCallback::ParallelFiringCallback(ParallelFiringControl &,IEventSubscription *,ICallFrame *,long *,long *,void *,void *)
0x180009a54  mov     rdi, rax
0x180009a57  test    rdi, rdi
0x180009a5a  jz      loc_180009B94
0x180009a60  mov     rdx, [rbx+50h]
0x180009a64  lea     rcx, [rbx+48h]
0x180009a68  call    ?NewNode@?$CList@PEAVParallelFiringCallback@@PEAV1@@@IEAAPEAUCNode@1@PEAU21@0@Z; CList<ParallelFiringCallback *,ParallelFiringCallback *>::NewNode(CList<ParallelFiringCallback *,ParallelFiringCallback *>::CNode *,CList<ParallelFiringCallback *,ParallelFiringCallback *>::CNode *)
0x180009a6d  test    rax, rax
0x180009a70  jnz     loc_180009BA6
0x180009a76  mov     eax, 8007000Eh
0x180009a7b  mov     [rsp+68h+var_28], eax
0x180009a7f  mov     eax, [rsp+68h+var_28]
0x180009a83  test    eax, eax
0x180009a85  js      loc_180009BC7
0x180009a8b  mov     rcx, [rbx+40h]; hEvent
0x180009a8f  call    cs:__imp_ResetEvent
0x180009a95  inc     dword ptr [rbx+38h]
0x180009a98  jmp     loc_180009BD4
0x180009a9d  mov     [rsp+68h+bstrString], 0
0x180009aa6  mov     rax, [rcx]
0x180009aa9  lea     rdx, [rsp+68h+bstrString]
0x180009aae  mov     rax, [rax+148h]
0x180009ab5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009aba  mov     rcx, [rsp+68h+arg_18]
0x180009ac2  mov     rax, [rcx]
0x180009ac5  mov     rax, [rax+10h]
0x180009ac9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009ace  mov     rdx, [rsp+68h+bstrString]; unsigned __int16 *
0x180009ad3  test    rdx, rdx
0x180009ad6  jz      loc_1800099A4
0x180009adc  mov     r8, [rsp+68h+arg_18]; struct IEventSubscription *
0x180009ae4  mov     rcx, rbx; this
0x180009ae7  call    ?FilterUsingCriteria@FiringControl@@IEAAJPEAGPEAUIEventSubscription@@@Z; FiringControl::FilterUsingCriteria(ushort *,IEventSubscription *)
0x180009aec  mov     [rsp+68h+var_28], eax
0x180009af0  mov     rcx, [rsp+68h+bstrString]; bstrString
0x180009af5  call    cs:__imp_SysFreeString
0x180009afb  mov     eax, [rsp+68h+var_28]
0x180009aff  test    eax, eax
0x180009b01  jz      loc_1800099A4
0x180009b07  mov     eax, 1
0x180009b0c  jmp     loc_180009BDA
0x180009b11  xor     edi, edi
0x180009b13  jmp     loc_180009A57
0x180009b18  mov     eax, 1
0x180009b1d  jmp     loc_180009BDA
0x180009b22  mov     eax, [rsp+68h+var_28]
0x180009b26  jmp     loc_180009BDA
0x180009b2b  test    rdi, rdi
0x180009b2e  jnz     loc_180009A60
0x180009b34  mov     edx, 1023h; unsigned int
0x180009b39  lea     r9d, [rdi+12h]; unsigned __int16
0x180009b3d  mov     r8d, 0C0001204h; unsigned int
0x180009b43  lea     rcx, aComComplusSrcE_10; "com\\complus\\src\\events\\tier1\\agent"...
0x180009b4a  call    ?InternalError@@YA_NPEBGKKG@Z; InternalError(ushort const *,ulong,ulong,ushort)
0x180009b4f  jmp     loc_180009A60
0x180009b54  xor     r9d, r9d; lpName
0x180009b57  lea     edx, [r9+1]; bManualReset
0x180009b5b  xor     ecx, ecx; lpEventAttributes
0x180009b5d  mov     r8d, edx; bInitialState
0x180009b60  call    cs:__imp_CreateEventW
0x180009b66  mov     [rbx+40h], rax
0x180009b6a  test    rax, rax
0x180009b6d  jnz     loc_1800099AF
0x180009b73  lea     r8d, [rax+12h]; unsigned __int16
0x180009b77  lea     r9, aCreateevent; "CreateEvent"
0x180009b7e  mov     edx, 0FFEh; unsigned int
0x180009b83  lea     rcx, aComComplusSrcE_10; "com\\complus\\src\\events\\tier1\\agent"...
0x180009b8a  call    ?InternalError_Win32@@YA_NPEBGKG0@Z; InternalError_Win32(ushort const *,ulong,ushort,ushort const *)
0x180009b8f  jmp     loc_1800099AF
0x180009b94  mov     rcx, [rsp+68h+TokenHandle]; hObject
0x180009b99  test    rcx, rcx
0x180009b9c  jz      short loc_180009B2B
0x180009b9e  call    cs:__imp_CloseHandle
0x180009ba4  jmp     short loc_180009B2B
0x180009ba6  mov     [rax+10h], rdi
0x180009baa  mov     rcx, [rbx+50h]
0x180009bae  test    rcx, rcx
0x180009bb1  jz      short loc_180009BB8
0x180009bb3  mov     [rcx], rax
0x180009bb6  jmp     short loc_180009BBC
0x180009bb8  mov     [rbx+48h], rax
0x180009bbc  mov     [rbx+50h], rax
0x180009bc0  xor     eax, eax
0x180009bc2  jmp     loc_180009A7B
0x180009bc7  test    rdi, rdi
0x180009bca  jz      short loc_180009BD4
0x180009bcc  mov     rcx, rdi; this
0x180009bcf  call    ??_GParallelFiringCallback@@QEAAPEAXI@Z; ParallelFiringCallback::`scalar deleting destructor'(uint)
0x180009bd4  jmp     short $+2
0x180009bd6  mov     eax, [rsp+68h+var_28]
0x180009bda  mov     rbx, [rsp+68h+arg_0]
0x180009bdf  mov     rsi, [rsp+68h+arg_8]
0x180009be4  add     rsp, 60h
0x180009be8  pop     rdi
0x180009be9  retn
0x180043837  push    rbp
0x180043839  sub     rsp, 40h
0x18004383d  mov     rbp, rdx
0x180043840  lea     rdx, [rbp+40h]; int *
0x180043844  call    ?ExceptionFilter@@YAKPEAU_EXCEPTION_POINTERS@@AEAJ@Z; ExceptionFilter(_EXCEPTION_POINTERS *,long &)
0x180043849  nop
0x18004384a  add     rsp, 40h
0x18004384e  pop     rbp
0x18004384f  retn
```
