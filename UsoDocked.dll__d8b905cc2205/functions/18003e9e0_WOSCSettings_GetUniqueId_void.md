# WOSCSettings::GetUniqueId(void)

- ea: `0x18003e9e0`
- end: `0x18003ea7c`
- name: `?GetUniqueId@WOSCSettings@@QEAA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@XZ`
- size: `156`
- prototype: ``
- caller_count: `2`
- callee_count: `4`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x1800248e0`
- `0x180042130`

## callees

- `0x18001ba70`
- `0x1800209fc`
- `0x18003e9e0`
- `0x180071010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18003ea53`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18003ea53`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18003ea1b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18003ea1b`

## string_xrefs

- `0x18003ea6a`: `onecore\enduser\windowsupdate\muse\common\lib\woscsettings.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall WOSCSettings::GetUniqueId(_QWORD *a1, __int64 a2)
{
  int v3; // eax
  PCWSTR StringRawBuffer; // rax
  __int64 v5; // r8
  int v7; // [rsp+20h] [rbp-18h]
  wil::details::in1diag3 *retaddr; // [rsp+38h] [rbp+0h]
  HSTRING string; // [rsp+40h] [rbp+8h] BYREF

  string = 0;
  v3 = (*(__int64 (__fastcall **)(_QWORD, HSTRING *))(*(_QWORD *)*a1 + 128LL))(*a1, &string);
  if ( v3 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x47,
      (unsigned int)"onecore\\enduser\\windowsupdate\\muse\\common\\lib\\woscsettings.cpp",
      (const char *)(unsigned int)v3,
      v7);
  StringRawBuffer = WindowsGetStringRawBuffer(string, 0);
  *(_OWORD *)a2 = 0;
  *(_QWORD *)(a2 + 16) = 0;
  *(_QWORD *)(a2 + 24) = 0;
  v5 = -1;
  do
    ++v5;
  while ( StringRawBuffer[v5] );
  std::wstring::_Construct<1,unsigned short const *>(a2, StringRawBuffer);
  if ( string )
    WindowsDeleteString(string);
  return a2;
}

```

## disassembly

```asm
0x18003e9e0  mov     [rsp+arg_8], rbx
0x18003e9e5  push    rdi
0x18003e9e6  sub     rsp, 30h
0x18003e9ea  mov     rbx, rdx
0x18003e9ed  xor     edi, edi
0x18003e9ef  mov     [rsp+38h+string], rdi
0x18003e9f4  mov     rcx, [rcx]
0x18003e9f7  mov     rax, [rcx]
0x18003e9fa  lea     rdx, [rsp+38h+string]
0x18003e9ff  mov     rax, [rax+80h]
0x18003ea06  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003ea0b  mov     rcx, [rsp+38h]; this
0x18003ea10  test    eax, eax
0x18003ea12  js      short loc_18003EA67
0x18003ea14  xor     edx, edx; length
0x18003ea16  mov     rcx, [rsp+38h+string]; string
0x18003ea1b  call    cs:__imp_WindowsGetStringRawBuffer
0x18003ea21  xorps   xmm0, xmm0
0x18003ea24  movups  xmmword ptr [rbx], xmm0
0x18003ea27  mov     [rbx+10h], rdi
0x18003ea2b  mov     [rbx+18h], rdi
0x18003ea2f  or      r8, 0FFFFFFFFFFFFFFFFh
0x18003ea33  inc     r8
0x18003ea36  cmp     [rax+r8*2], di
0x18003ea3b  jnz     short loc_18003EA33
0x18003ea3d  mov     rdx, rax
0x18003ea40  mov     rcx, rbx
0x18003ea43  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x18003ea48  nop
0x18003ea49  mov     rcx, [rsp+38h+string]; string
0x18003ea4e  test    rcx, rcx
0x18003ea51  jz      short loc_18003EA59
0x18003ea53  call    cs:__imp_WindowsDeleteString
0x18003ea59  mov     rax, rbx
0x18003ea5c  mov     rbx, [rsp+38h+arg_8]
0x18003ea61  add     rsp, 30h
0x18003ea65  pop     rdi
0x18003ea66  retn
0x18003ea67  mov     r9d, eax; char *
0x18003ea6a  lea     r8, aOnecoreEnduser_3; "onecore\\enduser\\windowsupdate\\muse\\"...
0x18003ea71  mov     edx, 47h ; 'G'; void *
0x18003ea76  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
```
