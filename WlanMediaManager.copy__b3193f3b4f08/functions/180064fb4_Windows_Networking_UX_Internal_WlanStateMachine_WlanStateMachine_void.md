# Windows::Networking::UX::Internal::WlanStateMachine::WlanStateMachine(void)

- ea: `0x180064fb4`
- end: `0x180065099`
- name: `??0WlanStateMachine@Internal@UX@Networking@Windows@@QEAA@XZ`
- size: `229`
- prototype: `__int64 __fastcall(Windows::Networking::UX::Internal::WlanStateMachine *__hidden this)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x18004ab7c`

## callees

- `0x180004a70`
- `0x18007d4bc`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180064fff`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180064fff`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionEx` at `0x180065055`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionEx` at `0x180065055`

## pseudocode

```c
// Hidden C++ exception states: #wind=9
Windows::Networking::UX::Internal::WlanStateMachine *__fastcall Windows::Networking::UX::Internal::WlanStateMachine::WlanStateMachine(
        Windows::Networking::UX::Internal::WlanStateMachine *this)
{
  *(_QWORD *)this = &Windows::Networking::UX::Internal::WlanStateMachine::`vftable';
  *((_QWORD *)this + 1) = 0;
  *((_QWORD *)this + 2) = 0;
  *((_QWORD *)this + 3) = 0;
  *((_WORD *)this + 16) = 0;
  *((_QWORD *)this + 7) = 0;
  *((_QWORD *)this + 8) = 0;
  *((_DWORD *)this + 18) = 0;
  *((_QWORD *)this + 10) = 0;
  *((_BYTE *)this + 88) = 0;
  *((_QWORD *)this + 30) = CreateEventW(0, 0, 0, 0);
  *((_QWORD *)this + 29) = 1;
  *((_QWORD *)this + 31) = 0;
  *((_QWORD *)this + 32) = 0;
  *((_QWORD *)this + 33) = 256;
  *((_BYTE *)this + 272) = 0;
  *(_QWORD *)((char *)this + 276) = 65537;
  *((_QWORD *)this + 36) = 0;
  InitializeCriticalSectionEx((LPCRITICAL_SECTION)((char *)this + 296), 0, 0);
  *((_DWORD *)this + 86) = 1;
  *((_QWORD *)this + 44) = 0;
  Windows::Networking::UX::Internal::GetCurrentEffectiveUserImpersonationToken((PHANDLE)this + 45);
  memset_0((char *)this + 104, 0, 0x80u);
  return this;
}

```

## disassembly

```asm
0x180064fb4  mov     [rsp+arg_8], rbx
0x180064fb9  mov     [rsp+arg_0], rcx
0x180064fbe  push    rsi
0x180064fbf  sub     rsp, 20h
0x180064fc3  mov     rbx, rcx
0x180064fc6  lea     rax, ??_7WlanStateMachine@Internal@UX@Networking@Windows@@6B@; const Windows::Networking::UX::Internal::WlanStateMachine::`vftable'
0x180064fcd  mov     [rcx], rax
0x180064fd0  xor     esi, esi
0x180064fd2  mov     [rcx+8], rsi
0x180064fd6  mov     [rcx+10h], rsi
0x180064fda  mov     [rcx+18h], rsi
0x180064fde  mov     [rcx+20h], si
0x180064fe2  mov     [rcx+38h], rsi
0x180064fe6  mov     [rcx+40h], rsi
0x180064fea  mov     [rcx+48h], esi
0x180064fed  mov     [rcx+50h], rsi
0x180064ff1  mov     [rcx+58h], sil
0x180064ff5  xor     r9d, r9d; lpName
0x180064ff8  xor     r8d, r8d; bInitialState
0x180064ffb  xor     edx, edx; bManualReset
0x180064ffd  xor     ecx, ecx; lpEventAttributes
0x180064fff  call    cs:__imp_CreateEventW
0x180065005  mov     [rbx+0F0h], rax
0x18006500c  mov     qword ptr [rbx+0E8h], 1
0x180065017  mov     [rbx+0F8h], rsi
0x18006501e  mov     [rbx+100h], rsi
0x180065025  mov     qword ptr [rbx+108h], 100h
0x180065030  mov     [rbx+110h], sil
0x180065037  mov     qword ptr [rbx+114h], 10001h
0x180065042  mov     [rbx+120h], rsi
0x180065049  lea     rcx, [rbx+128h]; lpCriticalSection
0x180065050  xor     r8d, r8d; Flags
0x180065053  xor     edx, edx; dwSpinCount
0x180065055  call    cs:__imp_InitializeCriticalSectionEx
0x18006505b  nop
0x18006505c  mov     dword ptr [rbx+158h], 1
0x180065066  mov     [rbx+160h], rsi
0x18006506d  lea     rcx, [rbx+168h]; phNewToken
0x180065074  call    ?GetCurrentEffectiveUserImpersonationToken@Internal@UX@Networking@Windows@@YA?AV?$unique_any_t@V?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@XZ; Windows::Networking::UX::Internal::GetCurrentEffectiveUserImpersonationToken(void)
0x180065079  lea     rcx, [rbx+68h]; void *
0x18006507d  xor     edx, edx; Val
0x18006507f  mov     r8d, 80h; Size
0x180065085  call    memset_0
0x18006508a  nop
0x18006508b  mov     rax, rbx
0x18006508e  mov     rbx, [rsp+28h+arg_8]
0x180065093  add     rsp, 20h
0x180065097  pop     rsi
0x180065098  retn
```
