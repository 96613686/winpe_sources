# CCPLUserMgrBroker::~CCPLUserMgrBroker(void)

- ea: `0x14000264c`
- end: `0x1400027ce`
- name: `??1CCPLUserMgrBroker@@EEAA@XZ`
- size: `386`
- prototype: `void __fastcall(CCPLUserMgrBroker *__hidden this)`
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x140002980`

## callees

- `0x14000264c`
- `0x140007010`

## import_xrefs

- `KERNEL32!UnregisterWait` at `0x14000267e`
- `KERNEL32!UnregisterWait` at `0x140002691`
- `KERNEL32!UnregisterWait` at `0x1400026a4`
- `KERNEL32!UnregisterWait` at `0x14000267e`
- `KERNEL32!UnregisterWait` at `0x140002691`
- `KERNEL32!UnregisterWait` at `0x1400026a4`
- `KERNEL32!CloseHandle` at `0x140002751`
- `KERNEL32!CloseHandle` at `0x140002769`
- `KERNEL32!CloseHandle` at `0x140002781`
- `KERNEL32!CloseHandle` at `0x140002799`
- `KERNEL32!CloseHandle` at `0x1400027b1`
- `KERNEL32!CloseHandle` at `0x140002751`
- `KERNEL32!CloseHandle` at `0x140002769`
- `KERNEL32!CloseHandle` at `0x140002781`
- `KERNEL32!CloseHandle` at `0x140002799`
- `KERNEL32!CloseHandle` at `0x1400027b1`

## pseudocode

```c
void __fastcall CCPLUserMgrBroker::~CCPLUserMgrBroker(CCPLUserMgrBroker *this)
{
  void *v2; // rcx
  void *v3; // rcx
  void *v4; // rcx
  int v5; // edx
  int v6; // edx
  int v7; // edx
  char *v8; // rcx
  char *v9; // rcx
  char *v10; // rcx
  char *v11; // rcx
  char *v12; // rcx

  *(_QWORD *)this = &CCPLUserMgrBroker::`vftable'{for `IUserManagementWizards'};
  *((_QWORD *)this + 1) = &CCPLUserMgrBroker::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,IUserManagementWizardsWithCancel>'};
  v2 = (void *)*((_QWORD *)this + 6);
  if ( v2 )
  {
    UnregisterWait(v2);
    *((_QWORD *)this + 6) = 0;
  }
  v3 = (void *)*((_QWORD *)this + 8);
  if ( v3 )
  {
    UnregisterWait(v3);
    *((_QWORD *)this + 8) = 0;
  }
  v4 = (void *)*((_QWORD *)this + 10);
  if ( v4 )
  {
    UnregisterWait(v4);
    *((_QWORD *)this + 10) = 0;
  }
  v5 = *((_DWORD *)this + 38);
  *((_QWORD *)this + 18) = &Windows::Internal::GitPtrImpl<Windows::Internal::GitPtr>::`vftable';
  if ( v5 )
  {
    if ( *((int *)this + 39) >= 0 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)qword_14000C868 + 32LL))(qword_14000C868);
    *((_DWORD *)this + 38) = 0;
  }
  v6 = *((_DWORD *)this + 34);
  *((_QWORD *)this + 16) = &Windows::Internal::GitPtrImpl<Windows::Internal::GitPtr>::`vftable';
  if ( v6 )
  {
    if ( *((int *)this + 35) >= 0 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)qword_14000C868 + 32LL))(qword_14000C868);
    *((_DWORD *)this + 34) = 0;
  }
  v7 = *((_DWORD *)this + 30);
  *((_QWORD *)this + 14) = &Windows::Internal::GitPtrImpl<Windows::Internal::GitPtr>::`vftable';
  if ( v7 )
  {
    if ( *((int *)this + 31) >= 0 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)qword_14000C868 + 32LL))(qword_14000C868);
    *((_DWORD *)this + 30) = 0;
  }
  v8 = (char *)*((_QWORD *)this + 9);
  *((_QWORD *)this + 9) = 0;
  if ( (unsigned __int64)(v8 - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
    CloseHandle(v8);
  v9 = (char *)*((_QWORD *)this + 7);
  *((_QWORD *)this + 7) = 0;
  if ( (unsigned __int64)(v9 - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
    CloseHandle(v9);
  v10 = (char *)*((_QWORD *)this + 5);
  *((_QWORD *)this + 5) = 0;
  if ( (unsigned __int64)(v10 - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
    CloseHandle(v10);
  v11 = (char *)*((_QWORD *)this + 4);
  *((_QWORD *)this + 4) = 0;
  if ( (unsigned __int64)(v11 - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
    CloseHandle(v11);
  v12 = (char *)*((_QWORD *)this + 3);
  *((_QWORD *)this + 3) = 0;
  if ( (unsigned __int64)(v12 - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
    CloseHandle(v12);
  *((_DWORD *)this + 5) = -1073741823;
}

```

## disassembly

```asm
0x14000264c  mov     [rsp+arg_0], rbx
0x140002651  mov     [rsp+arg_8], rsi
0x140002656  push    rdi
0x140002657  sub     rsp, 20h
0x14000265b  lea     rax, ??_7CCPLUserMgrBroker@@6BIUserManagementWizards@@@; const CCPLUserMgrBroker::`vftable'{for `IUserManagementWizards'}
0x140002662  mov     rbx, rcx
0x140002665  mov     [rcx], rax
0x140002668  xor     edi, edi
0x14000266a  lea     rax, ??_7CCPLUserMgrBroker@@6B?$ImplementsHelper@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00UIUserManagementWizardsWithCancel@@@Details@WRL@Microsoft@@@; const CCPLUserMgrBroker::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,IUserManagementWizardsWithCancel>'}
0x140002671  mov     [rcx+8], rax
0x140002675  mov     rcx, [rcx+30h]; WaitHandle
0x140002679  test    rcx, rcx
0x14000267c  jz      short loc_140002688
0x14000267e  call    cs:__imp_UnregisterWait
0x140002684  mov     [rbx+30h], rdi
0x140002688  mov     rcx, [rbx+40h]; WaitHandle
0x14000268c  test    rcx, rcx
0x14000268f  jz      short loc_14000269B
0x140002691  call    cs:__imp_UnregisterWait
0x140002697  mov     [rbx+40h], rdi
0x14000269b  mov     rcx, [rbx+50h]; WaitHandle
0x14000269f  test    rcx, rcx
0x1400026a2  jz      short loc_1400026AE
0x1400026a4  call    cs:__imp_UnregisterWait
0x1400026aa  mov     [rbx+50h], rdi
0x1400026ae  mov     edx, [rbx+98h]
0x1400026b4  lea     rsi, ??_7?$GitPtrImpl@VGitPtr@Internal@Windows@@@Internal@Windows@@6B@; const Windows::Internal::GitPtrImpl<Windows::Internal::GitPtr>::`vftable'
0x1400026bb  mov     [rbx+90h], rsi
0x1400026c2  test    edx, edx
0x1400026c4  jz      short loc_1400026E7
0x1400026c6  cmp     [rbx+9Ch], edi
0x1400026cc  jl      short loc_1400026E1
0x1400026ce  mov     rcx, cs:qword_14000C868
0x1400026d5  mov     rax, [rcx]
0x1400026d8  mov     rax, [rax+20h]
0x1400026dc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400026e1  mov     [rbx+98h], edi
0x1400026e7  mov     edx, [rbx+88h]
0x1400026ed  mov     [rbx+80h], rsi
0x1400026f4  test    edx, edx
0x1400026f6  jz      short loc_140002719
0x1400026f8  cmp     [rbx+8Ch], edi
0x1400026fe  jl      short loc_140002713
0x140002700  mov     rcx, cs:qword_14000C868
0x140002707  mov     rax, [rcx]
0x14000270a  mov     rax, [rax+20h]
0x14000270e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140002713  mov     [rbx+88h], edi
0x140002719  mov     edx, [rbx+78h]
0x14000271c  mov     [rbx+70h], rsi
0x140002720  test    edx, edx
0x140002722  jz      short loc_14000273F
0x140002724  cmp     [rbx+7Ch], edi
0x140002727  jl      short loc_14000273C
0x140002729  mov     rcx, cs:qword_14000C868
0x140002730  mov     rax, [rcx]
0x140002733  mov     rax, [rax+20h]
0x140002737  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000273c  mov     [rbx+78h], edi
0x14000273f  mov     rcx, [rbx+48h]; hObject
0x140002743  mov     [rbx+48h], rdi
0x140002747  lea     rax, [rcx-1]
0x14000274b  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x14000274f  ja      short loc_140002757
0x140002751  call    cs:__imp_CloseHandle
0x140002757  mov     rcx, [rbx+38h]; hObject
0x14000275b  mov     [rbx+38h], rdi
0x14000275f  lea     rax, [rcx-1]
0x140002763  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x140002767  ja      short loc_14000276F
0x140002769  call    cs:__imp_CloseHandle
0x14000276f  mov     rcx, [rbx+28h]; hObject
0x140002773  mov     [rbx+28h], rdi
0x140002777  lea     rax, [rcx-1]
0x14000277b  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x14000277f  ja      short loc_140002787
0x140002781  call    cs:__imp_CloseHandle
0x140002787  mov     rcx, [rbx+20h]; hObject
0x14000278b  mov     [rbx+20h], rdi
0x14000278f  lea     rax, [rcx-1]
0x140002793  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x140002797  ja      short loc_14000279F
0x140002799  call    cs:__imp_CloseHandle
0x14000279f  mov     rcx, [rbx+18h]; hObject
0x1400027a3  mov     [rbx+18h], rdi
0x1400027a7  lea     rax, [rcx-1]
0x1400027ab  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x1400027af  ja      short loc_1400027B7
0x1400027b1  call    cs:__imp_CloseHandle
0x1400027b7  mov     rsi, [rsp+28h+arg_8]
0x1400027bc  mov     dword ptr [rbx+14h], 0C0000001h
0x1400027c3  mov     rbx, [rsp+28h+arg_0]
0x1400027c8  add     rsp, 20h
0x1400027cc  pop     rdi
0x1400027cd  retn
```
