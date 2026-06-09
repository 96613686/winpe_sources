# Windows::UI::Input::Preview::Injection::InputInjector::UninitializeTouchInjection(void)

- ea: `0x18000e460`
- end: `0x18000e4f6`
- name: `?UninitializeTouchInjection@InputInjector@Injection@Preview@Input@UI@Windows@@UEAAJXZ`
- size: `150`
- prototype: `__int64 __fastcall(Windows::UI::Input::Preview::Injection::InputInjector *__hidden this)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x180009c10`

## callees

- `0x18000e460`
- `0x180010d48`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000e4e5`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000e4e5`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000e478`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000e478`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000e492`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000e492`
- `ext-ms-win-ntuser-rim-l1-1-0!RemoveInjectionDevice` at `0x18000e488`
- `ext-ms-win-ntuser-rim-l1-1-0!RemoveInjectionDevice` at `0x18000e488`

## pseudocode

```c
__int64 __fastcall Windows::UI::Input::Preview::Injection::InputInjector::UninitializeTouchInjection(
        Windows::UI::Input::Preview::Injection::InputInjector *this)
{
  struct _RTL_CRITICAL_SECTION *v1; // rsi
  unsigned int v3; // edi
  struct Windows::UI::Input::Preview::Injection::TouchTelemetry *v4; // rdx
  __int64 v5; // rcx
  signed int LastError; // eax
  __int128 v8; // [rsp+40h] [rbp-48h]

  v1 = (struct _RTL_CRITICAL_SECTION *)((char *)this + 128);
  v3 = 0;
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 128));
  v5 = *((_QWORD *)this + 11);
  if ( v5 != -1 && !(unsigned int)RemoveInjectionDevice(v5) )
  {
    LastError = GetLastError();
    v3 = LastError;
    if ( LastError > 0 )
      v3 = (unsigned __int16)LastError | 0x80070000;
  }
  Windows::UI::Input::Preview::Injection::WriteTouchTelemetry(
    (Windows::UI::Input::Preview::Injection::InputInjector *)((char *)this + 244),
    v4);
  *((_QWORD *)this + 11) = 0;
  *(_OWORD *)((char *)this + 244) = 0;
  v8 = 0;
  *(_OWORD *)((char *)this + 260) = 0;
  HIDWORD(v8) = 0;
  *(_OWORD *)((char *)this + 276) = v8;
  *((_OWORD *)this + 18) = 0;
  if ( v1 )
    LeaveCriticalSection(v1);
  return v3;
}

```

## disassembly

```asm
0x18000e460  push    rbx
0x18000e462  push    rbp
0x18000e463  push    rsi
0x18000e464  push    rdi
0x18000e465  sub     rsp, 68h
0x18000e469  lea     rsi, [rcx+80h]
0x18000e470  mov     rbp, rcx
0x18000e473  mov     rcx, rsi; lpCriticalSection
0x18000e476  xor     edi, edi
0x18000e478  call    cs:__imp_EnterCriticalSection
0x18000e47e  mov     rcx, [rbp+58h]
0x18000e482  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x18000e486  jz      short loc_18000E4A7
0x18000e488  call    cs:__imp_RemoveInjectionDevice
0x18000e48e  test    eax, eax
0x18000e490  jnz     short loc_18000E4A7
0x18000e492  call    cs:__imp_GetLastError
0x18000e498  mov     edi, eax
0x18000e49a  test    eax, eax
0x18000e49c  jle     short loc_18000E4A7
0x18000e49e  movzx   edi, ax
0x18000e4a1  or      edi, 80070000h
0x18000e4a7  lea     rbx, [rbp+0F4h]
0x18000e4ae  mov     rcx, rbx; this
0x18000e4b1  call    ?WriteTouchTelemetry@Injection@Preview@Input@UI@Windows@@YAXAEAUTouchTelemetry@12345@@Z; Windows::UI::Input::Preview::Injection::WriteTouchTelemetry(Windows::UI::Input::Preview::Injection::TouchTelemetry &)
0x18000e4b6  xorps   xmm1, xmm1
0x18000e4b9  xor     eax, eax
0x18000e4bb  mov     [rbp+58h], rax
0x18000e4bf  movups  xmmword ptr [rbx], xmm1
0x18000e4c2  movups  [rsp+88h+var_48], xmm1
0x18000e4c7  movups  xmmword ptr [rbx+10h], xmm1
0x18000e4cb  movups  [rsp+88h+var_48+0Ch], xmm1
0x18000e4d0  movups  xmm0, [rsp+88h+var_48]
0x18000e4d5  movups  xmmword ptr [rbx+20h], xmm0
0x18000e4d9  movups  xmmword ptr [rbx+2Ch], xmm1
0x18000e4dd  test    rsi, rsi
0x18000e4e0  jz      short loc_18000E4EB
0x18000e4e2  mov     rcx, rsi; lpCriticalSection
0x18000e4e5  call    cs:__imp_LeaveCriticalSection
0x18000e4eb  mov     eax, edi
0x18000e4ed  add     rsp, 68h
0x18000e4f1  pop     rdi
0x18000e4f2  pop     rsi
0x18000e4f3  pop     rbp
0x18000e4f4  pop     rbx
0x18000e4f5  retn
```
