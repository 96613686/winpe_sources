# Windows::UI::Input::Preview::Injection::InputInjector::UninitializeButtonInjection(void)

- ea: `0x18000e2bc`
- end: `0x18000e33a`
- name: `?UninitializeButtonInjection@InputInjector@Injection@Preview@Input@UI@Windows@@AEAAJXZ`
- size: `126`
- prototype: `__int64 __fastcall(Windows::UI::Input::Preview::Injection::InputInjector *__hidden this)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x180009c10`
- `0x18000abd0`

## callees

- `0x18000e2bc`
- `0x1800106f0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000e329`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000e329`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000e2d4`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000e2d4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000e2ee`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000e2ee`
- `ext-ms-win-ntuser-rim-l1-1-0!RemoveInjectionDevice` at `0x18000e2e4`
- `ext-ms-win-ntuser-rim-l1-1-0!RemoveInjectionDevice` at `0x18000e2e4`

## pseudocode

```c
__int64 __fastcall Windows::UI::Input::Preview::Injection::InputInjector::UninitializeButtonInjection(
        Windows::UI::Input::Preview::Injection::InputInjector *this)
{
  struct _RTL_CRITICAL_SECTION *v1; // rsi
  unsigned int v3; // edi
  struct Windows::UI::Input::Preview::Injection::ButtonTelemetry *v4; // rdx
  __int64 v5; // rcx
  signed int LastError; // eax

  v1 = (struct _RTL_CRITICAL_SECTION *)((char *)this + 128);
  v3 = 0;
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 128));
  v5 = *((_QWORD *)this + 14);
  if ( v5 != -1 && !(unsigned int)RemoveInjectionDevice(v5) )
  {
    LastError = GetLastError();
    v3 = LastError;
    if ( LastError > 0 )
      v3 = (unsigned __int16)LastError | 0x80070000;
  }
  Windows::UI::Input::Preview::Injection::WriteButtonTelemetry(
    (Windows::UI::Input::Preview::Injection::InputInjector *)((char *)this + 412),
    v4);
  *((_QWORD *)this + 14) = 0;
  *(_OWORD *)((char *)this + 412) = 0;
  *((_DWORD *)this + 107) = 0;
  if ( v1 )
    LeaveCriticalSection(v1);
  return v3;
}

```

## disassembly

```asm
0x18000e2bc  push    rbx
0x18000e2be  push    rbp
0x18000e2bf  push    rsi
0x18000e2c0  push    rdi
0x18000e2c1  sub     rsp, 28h
0x18000e2c5  lea     rsi, [rcx+80h]
0x18000e2cc  mov     rbp, rcx
0x18000e2cf  mov     rcx, rsi; lpCriticalSection
0x18000e2d2  xor     edi, edi
0x18000e2d4  call    cs:__imp_EnterCriticalSection
0x18000e2da  mov     rcx, [rbp+70h]
0x18000e2de  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x18000e2e2  jz      short loc_18000E303
0x18000e2e4  call    cs:__imp_RemoveInjectionDevice
0x18000e2ea  test    eax, eax
0x18000e2ec  jnz     short loc_18000E303
0x18000e2ee  call    cs:__imp_GetLastError
0x18000e2f4  mov     edi, eax
0x18000e2f6  test    eax, eax
0x18000e2f8  jle     short loc_18000E303
0x18000e2fa  movzx   edi, ax
0x18000e2fd  or      edi, 80070000h
0x18000e303  lea     rbx, [rbp+19Ch]
0x18000e30a  mov     rcx, rbx; this
0x18000e30d  call    ?WriteButtonTelemetry@Injection@Preview@Input@UI@Windows@@YAXAEAUButtonTelemetry@12345@@Z; Windows::UI::Input::Preview::Injection::WriteButtonTelemetry(Windows::UI::Input::Preview::Injection::ButtonTelemetry &)
0x18000e312  xor     eax, eax
0x18000e314  xorps   xmm0, xmm0
0x18000e317  mov     [rbp+70h], rax
0x18000e31b  movups  xmmword ptr [rbx], xmm0
0x18000e31e  mov     [rbx+10h], eax
0x18000e321  test    rsi, rsi
0x18000e324  jz      short loc_18000E32F
0x18000e326  mov     rcx, rsi; lpCriticalSection
0x18000e329  call    cs:__imp_LeaveCriticalSection
0x18000e32f  mov     eax, edi
0x18000e331  add     rsp, 28h
0x18000e335  pop     rdi
0x18000e336  pop     rsi
0x18000e337  pop     rbp
0x18000e338  pop     rbx
0x18000e339  retn
```
