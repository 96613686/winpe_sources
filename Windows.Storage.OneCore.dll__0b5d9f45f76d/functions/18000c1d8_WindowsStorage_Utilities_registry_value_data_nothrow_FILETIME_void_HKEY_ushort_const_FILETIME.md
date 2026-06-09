# WindowsStorage::Utilities::registry_value_data_nothrow<_FILETIME,void>(HKEY__ *,ushort const *,_FILETIME *)

- ea: `0x18000c1d8`
- end: `0x18000c23a`
- name: `??$registry_value_data_nothrow@U_FILETIME@@X@Utilities@WindowsStorage@@YAJPEAUHKEY__@@PEBGPEAU_FILETIME@@@Z`
- size: `98`
- prototype: `int __fastcall(HKEY, __int64, void *)`
- caller_count: `2`
- callee_count: `2`
- tags: `registry_config, installer_update`

## callers

- `0x18000e2fc`
- `0x18000fa4c`

## callees

- `0x18000c1d8`
- `0x18000f040`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18000c20e`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18000c20e`

## string_xrefs

- `0x18000c21d`: `onecore\base\windows.storage\src\Registry.h`
- `0x18000c1ff`: `LastUpdatedTime`

## pseudocode

```c
int __fastcall WindowsStorage::Utilities::registry_value_data_nothrow<_FILETIME,void>(HKEY a1, __int64 a2, void *a3)
{
  unsigned int ValueW; // eax
  unsigned int v5; // [rsp+20h] [rbp-28h]
  wil::details::in1diag3 *retaddr; // [rsp+48h] [rbp+0h]
  DWORD v7; // [rsp+58h] [rbp+10h] BYREF
  int v8; // [rsp+5Ch] [rbp+14h]

  v8 = HIDWORD(a2);
  v7 = 8;
  ValueW = RegGetValueW(a1, 0, L"LastUpdatedTime", 0xFFFFu, 0, a3, &v7);
  if ( ValueW )
    return wil::details::in1diag3::Return_Win32(
             retaddr,
             (void *)0x100,
             (unsigned int)"onecore\\base\\windows.storage\\src\\Registry.h",
             (const char *)ValueW,
             v5);
  else
    return 0;
}

```

## disassembly

```asm
0x18000c1d8  mov     r11, rsp
0x18000c1db  mov     [r11+10h], rdx
0x18000c1df  sub     rsp, 48h
0x18000c1e3  lea     rax, [r11+10h]
0x18000c1e7  mov     [rsp+48h+arg_8], 8
0x18000c1ef  mov     [r11-18h], rax
0x18000c1f3  mov     r9d, 0FFFFh; dwFlags
0x18000c1f9  mov     [r11-20h], r8
0x18000c1fd  xor     edx, edx; lpSubKey
0x18000c1ff  lea     r8, aLastupdatedtim; "LastUpdatedTime"
0x18000c206  mov     qword ptr [r11-28h], 0
0x18000c20e  call    cs:__imp_RegGetValueW
0x18000c214  test    eax, eax
0x18000c216  jz      short loc_18000C233
0x18000c218  mov     rcx, [rsp+48h]; this
0x18000c21d  lea     r8, aOnecoreBaseWin_7; "onecore\\base\\windows.storage\\src\\Re"...
0x18000c224  mov     r9d, eax; char *
0x18000c227  mov     edx, 100h; void *
0x18000c22c  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x18000c231  jmp     short loc_18000C235
0x18000c233  xor     eax, eax
0x18000c235  add     rsp, 48h
0x18000c239  retn
```
