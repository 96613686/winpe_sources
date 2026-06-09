# Windows::UI::Input::Preview::Injection::InputInjector::UninitializePenInjection(void)

- ea: `0x18000e3d0`
- end: `0x18000e457`
- name: `?UninitializePenInjection@InputInjector@Injection@Preview@Input@UI@Windows@@UEAAJXZ`
- size: `135`
- prototype: `__int64 __fastcall(Windows::UI::Input::Preview::Injection::InputInjector *__hidden this)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x180009c10`

## callees

- `0x18000e3d0`
- `0x180010aac`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000e446`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000e446`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000e3e8`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000e3e8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000e402`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000e402`
- `ext-ms-win-ntuser-rim-l1-1-0!RemoveInjectionDevice` at `0x18000e3f8`
- `ext-ms-win-ntuser-rim-l1-1-0!RemoveInjectionDevice` at `0x18000e3f8`

## pseudocode

```c
__int64 __fastcall Windows::UI::Input::Preview::Injection::InputInjector::UninitializePenInjection(
        Windows::UI::Input::Preview::Injection::InputInjector *this)
{
  struct _RTL_CRITICAL_SECTION *v1; // rsi
  unsigned int v3; // edi
  struct Windows::UI::Input::Preview::Injection::PenTelemetry *v4; // rdx
  __int64 v5; // rcx
  signed int LastError; // eax

  v1 = (struct _RTL_CRITICAL_SECTION *)((char *)this + 128);
  v3 = 0;
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 128));
  v5 = *((_QWORD *)this + 12);
  if ( v5 != -1 && !(unsigned int)RemoveInjectionDevice(v5) )
  {
    LastError = GetLastError();
    v3 = LastError;
    if ( LastError > 0 )
      v3 = (unsigned __int16)LastError | 0x80070000;
  }
  Windows::UI::Input::Preview::Injection::WritePenTelemetry(
    (Windows::UI::Input::Preview::Injection::InputInjector *)((char *)this + 188),
    v4);
  *((_QWORD *)this + 12) = 0;
  *(_OWORD *)((char *)this + 188) = 0;
  *(_OWORD *)((char *)this + 204) = 0;
  *(_OWORD *)((char *)this + 220) = 0;
  *(_QWORD *)((char *)this + 236) = 0;
  if ( v1 )
    LeaveCriticalSection(v1);
  return v3;
}

```

## disassembly

```asm
0x18000e3d0  push    rbx
0x18000e3d2  push    rbp
0x18000e3d3  push    rsi
0x18000e3d4  push    rdi
0x18000e3d5  sub     rsp, 28h
0x18000e3d9  lea     rsi, [rcx+80h]
0x18000e3e0  mov     rbp, rcx
0x18000e3e3  mov     rcx, rsi; lpCriticalSection
0x18000e3e6  xor     edi, edi
0x18000e3e8  call    cs:__imp_EnterCriticalSection
0x18000e3ee  mov     rcx, [rbp+60h]
0x18000e3f2  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x18000e3f6  jz      short loc_18000E417
0x18000e3f8  call    cs:__imp_RemoveInjectionDevice
0x18000e3fe  test    eax, eax
0x18000e400  jnz     short loc_18000E417
0x18000e402  call    cs:__imp_GetLastError
0x18000e408  mov     edi, eax
0x18000e40a  test    eax, eax
0x18000e40c  jle     short loc_18000E417
0x18000e40e  movzx   edi, ax
0x18000e411  or      edi, 80070000h
0x18000e417  lea     rbx, [rbp+0BCh]
0x18000e41e  mov     rcx, rbx; this
0x18000e421  call    ?WritePenTelemetry@Injection@Preview@Input@UI@Windows@@YAXAEAUPenTelemetry@12345@@Z; Windows::UI::Input::Preview::Injection::WritePenTelemetry(Windows::UI::Input::Preview::Injection::PenTelemetry &)
0x18000e426  xorps   xmm0, xmm0
0x18000e429  xor     eax, eax
0x18000e42b  mov     [rbp+60h], rax
0x18000e42f  movups  xmmword ptr [rbx], xmm0
0x18000e432  movups  xmmword ptr [rbx+10h], xmm0
0x18000e436  movups  xmmword ptr [rbx+20h], xmm0
0x18000e43a  mov     [rbx+30h], rax
0x18000e43e  test    rsi, rsi
0x18000e441  jz      short loc_18000E44C
0x18000e443  mov     rcx, rsi; lpCriticalSection
0x18000e446  call    cs:__imp_LeaveCriticalSection
0x18000e44c  mov     eax, edi
0x18000e44e  add     rsp, 28h
0x18000e452  pop     rdi
0x18000e453  pop     rsi
0x18000e454  pop     rbp
0x18000e455  pop     rbx
0x18000e456  retn
```
