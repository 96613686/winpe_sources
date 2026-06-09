# Windows::UI::Input::Preview::Injection::InputInjector::InitializeGamepadInjection(void)

- ea: `0x18000ace0`
- end: `0x18000ad95`
- name: `?InitializeGamepadInjection@InputInjector@Injection@Preview@Input@UI@Windows@@UEAAJXZ`
- size: `181`
- prototype: `__int64 __fastcall(Windows::UI::Input::Preview::Injection::InputInjector *__hidden this)`
- caller_count: `0`
- callee_count: `3`
- tags: `installer_update`

## callees

- `0x18000ace0`
- `0x18000e580`
- `0x180012010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000ad3e`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000ad83`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000ad3e`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000ad83`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000acf4`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000acf4`
- `XboxgipSynthetic!SyntheticController_Connect` at `0x18000ad65`
- `XboxgipSynthetic!SyntheticController_Connect` at `0x18000ad65`
- `XboxgipSynthetic!SyntheticController_CreateController` at `0x18000ad18`
- `XboxgipSynthetic!SyntheticController_CreateController` at `0x18000ad18`

## pseudocode

```c
__int64 __fastcall Windows::UI::Input::Preview::Injection::InputInjector::InitializeGamepadInjection(
        Windows::UI::Input::Preview::Injection::InputInjector *this)
{
  struct _RTL_CRITICAL_SECTION *v1; // rsi
  int Controller; // edi

  v1 = (struct _RTL_CRITICAL_SECTION *)((char *)this + 112);
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 112));
  (*(void (__fastcall **)(Windows::UI::Input::Preview::Injection::InputInjector *))(*(_QWORD *)this + 64LL))(this);
  if ( *((_QWORD *)this + 11) )
    goto LABEL_7;
  Controller = SyntheticController_CreateController(0, (char *)this + 88);
  if ( Controller == -2147024891 )
  {
    *((_BYTE *)this + 420) = 0;
    *((_DWORD *)this + 95) = -2147024891;
    if ( v1 )
      LeaveCriticalSection(v1);
    return 0;
  }
  *((_BYTE *)this + 420) = 1;
  if ( Controller >= 0 )
  {
LABEL_7:
    Controller = Windows::UI::Input::Preview::Injection::InputInjector::UpdateGamepadTargetProcess((Windows::UI::Input::Preview::Injection::InputInjector *)((char *)this - 16));
    if ( Controller >= 0 )
    {
      Controller = SyntheticController_Connect(*((_QWORD *)this + 11));
      *((_BYTE *)this + 104) = Controller >= 0;
    }
  }
  *((_DWORD *)this + 95) = Controller;
  if ( v1 )
    LeaveCriticalSection(v1);
  return (unsigned int)Controller;
}

```

## disassembly

```asm
0x18000ace0  push    rbx
0x18000ace2  push    rsi
0x18000ace3  push    rdi
0x18000ace4  push    r14
0x18000ace6  sub     rsp, 28h
0x18000acea  lea     rsi, [rcx+70h]
0x18000acee  mov     rbx, rcx
0x18000acf1  mov     rcx, rsi; lpCriticalSection
0x18000acf4  call    cs:__imp_EnterCriticalSection
0x18000acfa  mov     rax, [rbx]
0x18000acfd  mov     rcx, rbx
0x18000ad00  mov     rax, [rax+40h]
0x18000ad04  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ad09  lea     r14, [rbx+58h]
0x18000ad0d  cmp     qword ptr [r14], 0
0x18000ad11  jnz     short loc_18000AD53
0x18000ad13  mov     rdx, r14
0x18000ad16  xor     ecx, ecx
0x18000ad18  call    cs:__imp_SyntheticController_CreateController
0x18000ad1e  mov     edi, eax
0x18000ad20  mov     eax, 80070005h
0x18000ad25  cmp     edi, eax
0x18000ad27  jnz     short loc_18000AD48
0x18000ad29  mov     byte ptr [rbx+1A4h], 0
0x18000ad30  mov     [rbx+17Ch], eax
0x18000ad36  test    rsi, rsi
0x18000ad39  jz      short loc_18000AD44
0x18000ad3b  mov     rcx, rsi; lpCriticalSection
0x18000ad3e  call    cs:__imp_LeaveCriticalSection
0x18000ad44  xor     eax, eax
0x18000ad46  jmp     short loc_18000AD8B
0x18000ad48  mov     byte ptr [rbx+1A4h], 1
0x18000ad4f  test    edi, edi
0x18000ad51  js      short loc_18000AD75
0x18000ad53  lea     rcx, [rbx-10h]; this
0x18000ad57  call    ?UpdateGamepadTargetProcess@InputInjector@Injection@Preview@Input@UI@Windows@@AEAAJXZ; Windows::UI::Input::Preview::Injection::InputInjector::UpdateGamepadTargetProcess(void)
0x18000ad5c  mov     edi, eax
0x18000ad5e  test    eax, eax
0x18000ad60  js      short loc_18000AD75
0x18000ad62  mov     rcx, [r14]
0x18000ad65  call    cs:__imp_SyntheticController_Connect
0x18000ad6b  mov     edi, eax
0x18000ad6d  shr     eax, 1Fh
0x18000ad70  xor     al, 1
0x18000ad72  mov     [rbx+68h], al
0x18000ad75  mov     [rbx+17Ch], edi
0x18000ad7b  test    rsi, rsi
0x18000ad7e  jz      short loc_18000AD89
0x18000ad80  mov     rcx, rsi; lpCriticalSection
0x18000ad83  call    cs:__imp_LeaveCriticalSection
0x18000ad89  mov     eax, edi
0x18000ad8b  add     rsp, 28h
0x18000ad8f  pop     r14
0x18000ad91  pop     rdi
0x18000ad92  pop     rsi
0x18000ad93  pop     rbx
0x18000ad94  retn
```
