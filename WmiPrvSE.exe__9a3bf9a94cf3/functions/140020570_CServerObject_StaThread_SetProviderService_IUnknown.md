# CServerObject_StaThread::SetProviderService(IUnknown *)

- ea: `0x140020570`
- end: `0x140020739`
- name: `?SetProviderService@CServerObject_StaThread@@QEAAJPEAUIUnknown@@@Z`
- size: `457`
- prototype: `__int64 __fastcall(CServerObject_StaThread *__hidden this, struct IUnknown *)`
- caller_count: `1`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callers

- `0x14001e910`

## callees

- `0x140020570`
- `0x1400234b8`
- `0x140048010`

## import_xrefs

- `wbemcomn!GetMemLogObject` at `0x1400206e3`
- `wbemcomn!GetMemLogObject` at `0x1400206e3`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x1400206ee`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x1400206ee`

## pseudocode

```c
__int64 __fastcall CServerObject_StaThread::SetProviderService(CServerObject_StaThread *this, struct IUnknown *a2)
{
  int v4; // ebx
  int v5; // eax
  int v6; // eax
  int v7; // eax
  int v8; // eax
  int v9; // eax
  int v10; // eax
  int v11; // eax
  CMemoryLog *MemLogObject; // rax

  if ( !a2 )
  {
    v4 = -2147217400;
LABEL_18:
    MemLogObject = GetMemLogObject();
    CMemoryLog::Write(MemLogObject, v4);
    goto LABEL_13;
  }
  *((_QWORD *)this + 60) = a2;
  v4 = 0;
  ((void (__fastcall *)(struct IUnknown *))a2->lpVtbl->AddRef)(a2);
  v5 = ((__int64 (__fastcall *)(struct IUnknown *, GUID *, char *))a2->lpVtbl->QueryInterface)(
         a2,
         &IID_IWbemServices,
         (char *)this + 488);
  if ( v5 != -2147467262 )
  {
    v4 = v5;
    if ( v5 < 0 )
      goto LABEL_18;
  }
  v6 = ((__int64 (__fastcall *)(struct IUnknown *, GUID *, char *))a2->lpVtbl->QueryInterface)(
         a2,
         &IID_IWbemEventConsumerProvider,
         (char *)this + 496);
  if ( v6 != -2147467262 )
  {
    v4 = v6;
    if ( v6 < 0 )
      goto LABEL_18;
  }
  v7 = ((__int64 (__fastcall *)(struct IUnknown *, GUID *, char *))a2->lpVtbl->QueryInterface)(
         a2,
         &IID_IWbemEventConsumerProviderEx,
         (char *)this + 504);
  if ( v7 != -2147467262 )
  {
    v4 = v7;
    if ( v7 < 0 )
      goto LABEL_18;
  }
  v8 = ((__int64 (__fastcall *)(struct IUnknown *, GUID *, char *))a2->lpVtbl->QueryInterface)(
         a2,
         &IID_IWbemUnboundObjectSink,
         (char *)this + 512);
  if ( v8 != -2147467262 )
  {
    v4 = v8;
    if ( v8 < 0 )
      goto LABEL_18;
  }
  v9 = ((__int64 (__fastcall *)(struct IUnknown *, GUID *, char *))a2->lpVtbl->QueryInterface)(
         a2,
         &IID_IWbemEventProvider,
         (char *)this + 520);
  if ( v9 != -2147467262 )
  {
    v4 = v9;
    if ( v9 < 0 )
      goto LABEL_18;
  }
  v10 = ((__int64 (__fastcall *)(struct IUnknown *, GUID *, char *))a2->lpVtbl->QueryInterface)(
          a2,
          &IID_IWbemEventProviderQuerySink,
          (char *)this + 528);
  if ( v10 != -2147467262 )
  {
    v4 = v10;
    if ( v10 < 0 )
      goto LABEL_18;
  }
  v11 = ((__int64 (__fastcall *)(struct IUnknown *, GUID *, char *))a2->lpVtbl->QueryInterface)(
          a2,
          &IID_IWbemEventProviderSecurity,
          (char *)this + 536);
  if ( v11 != -2147467262 )
    v4 = v11;
  if ( v4 < 0 )
    goto LABEL_18;
LABEL_13:
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 15, WPP_d3ea76c96a8339db06b7a6ae92e79012_Traceguids, (unsigned int)v4);
  }
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x140020570  push    rbx
0x140020572  push    rbp
0x140020573  push    rsi
0x140020574  push    rdi
0x140020575  sub     rsp, 28h
0x140020579  mov     rdi, rdx
0x14002057c  mov     rsi, rcx
0x14002057f  test    rdx, rdx
0x140020582  jz      loc_1400206D2
0x140020588  mov     [rcx+1E0h], rdx
0x14002058f  xor     ebx, ebx
0x140020591  mov     rax, [rdx]
0x140020594  mov     rcx, rdx
0x140020597  mov     rax, [rax+8]
0x14002059b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400205a0  mov     rax, [rdi]
0x1400205a3  lea     r8, [rsi+1E8h]
0x1400205aa  lea     rdx, IID_IWbemServices
0x1400205b1  mov     rcx, rdi
0x1400205b4  mov     rax, [rax]
0x1400205b7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400205bc  mov     ebp, 80004002h
0x1400205c1  cmp     eax, ebp
0x1400205c3  jnz     loc_1400206D9
0x1400205c9  mov     rax, [rdi]
0x1400205cc  lea     r8, [rsi+1F0h]
0x1400205d3  lea     rdx, IID_IWbemEventConsumerProvider
0x1400205da  mov     rcx, rdi
0x1400205dd  mov     rax, [rax]
0x1400205e0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400205e5  cmp     eax, ebp
0x1400205e7  jz      short loc_1400205F3
0x1400205e9  mov     ebx, eax
0x1400205eb  test    eax, eax
0x1400205ed  js      loc_1400206E3
0x1400205f3  mov     rax, [rdi]
0x1400205f6  lea     r8, [rsi+1F8h]
0x1400205fd  lea     rdx, IID_IWbemEventConsumerProviderEx
0x140020604  mov     rcx, rdi
0x140020607  mov     rax, [rax]
0x14002060a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14002060f  cmp     eax, ebp
0x140020611  jnz     loc_1400206F6
0x140020617  mov     rax, [rdi]
0x14002061a  lea     r8, [rsi+200h]
0x140020621  lea     rdx, IID_IWbemUnboundObjectSink
0x140020628  mov     rcx, rdi
0x14002062b  mov     rax, [rax]
0x14002062e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140020633  cmp     eax, ebp
0x140020635  jz      short loc_140020641
0x140020637  mov     ebx, eax
0x140020639  test    eax, eax
0x14002063b  js      loc_1400206E3
0x140020641  mov     rax, [rdi]
0x140020644  lea     r8, [rsi+208h]
0x14002064b  lea     rdx, IID_IWbemEventProvider
0x140020652  mov     rcx, rdi
0x140020655  mov     rax, [rax]
0x140020658  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14002065d  cmp     eax, ebp
0x14002065f  jnz     loc_140020701
0x140020665  mov     rax, [rdi]
0x140020668  lea     r8, [rsi+210h]
0x14002066f  lea     rdx, IID_IWbemEventProviderQuerySink
0x140020676  mov     rcx, rdi
0x140020679  mov     rax, [rax]
0x14002067c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140020681  cmp     eax, ebp
0x140020683  jnz     loc_14002070D
0x140020689  mov     rax, [rdi]
0x14002068c  lea     r8, [rsi+218h]
0x140020693  lea     rdx, IID_IWbemEventProviderSecurity
0x14002069a  mov     rcx, rdi
0x14002069d  mov     rax, [rax]
0x1400206a0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400206a5  cmp     eax, ebp
0x1400206a7  cmovnz  ebx, eax
0x1400206aa  test    ebx, ebx
0x1400206ac  js      short loc_1400206E3
0x1400206ae  mov     rcx, cs:WPP_GLOBAL_Control
0x1400206b5  lea     rax, WPP_GLOBAL_Control
0x1400206bc  cmp     rcx, rax
0x1400206bf  jz      short loc_1400206C7
0x1400206c1  test    byte ptr [rcx+1Ch], 4
0x1400206c5  jnz     short loc_140020719
0x1400206c7  mov     eax, ebx
0x1400206c9  add     rsp, 28h
0x1400206cd  pop     rdi
0x1400206ce  pop     rsi
0x1400206cf  pop     rbp
0x1400206d0  pop     rbx
0x1400206d1  retn
0x1400206d2  mov     ebx, 80041008h
0x1400206d7  jmp     short loc_1400206E3
0x1400206d9  mov     ebx, eax
0x1400206db  test    eax, eax
0x1400206dd  jns     loc_1400205C9
0x1400206e3  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x1400206e9  mov     rcx, rax
0x1400206ec  mov     edx, ebx
0x1400206ee  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x1400206f4  jmp     short loc_1400206AE
0x1400206f6  mov     ebx, eax
0x1400206f8  test    eax, eax
0x1400206fa  js      short loc_1400206E3
0x1400206fc  jmp     loc_140020617
0x140020701  mov     ebx, eax
0x140020703  test    eax, eax
0x140020705  jns     loc_140020665
0x14002070b  jmp     short loc_1400206E3
0x14002070d  mov     ebx, eax
0x14002070f  test    eax, eax
0x140020711  jns     loc_140020689
0x140020717  jmp     short loc_1400206E3
0x140020719  cmp     byte ptr [rcx+19h], 2
0x14002071d  jb      short loc_1400206C7
0x14002071f  mov     rcx, [rcx+10h]
0x140020723  lea     r8, WPP_d3ea76c96a8339db06b7a6ae92e79012_Traceguids
0x14002072a  mov     edx, 0Fh
0x14002072f  mov     r9d, ebx
0x140020732  call    WPP_SF_d
0x140020737  jmp     short loc_1400206C7
```
