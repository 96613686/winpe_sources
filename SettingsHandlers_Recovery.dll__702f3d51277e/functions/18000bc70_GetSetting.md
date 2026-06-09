# GetSetting

- ea: `0x18000bc70`
- end: `0x18000bdc4`
- name: `GetSetting`
- size: `340`
- prototype: `__int64 __fastcall(HSTRING string, _QWORD *)`
- caller_count: `0`
- callee_count: `3`
- tags: `registry_config, loader_planting, broker_com_uri`

## callees

- `0x18000b784`
- `0x18000bc70`
- `0x18002b010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18000bc98`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18000bd19`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18000bd7d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18000bc98`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18000bd19`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18000bd7d`

## string_xrefs

- `0x18000bd38`: `OneCoreUap\Internal\Shell\inc\SettingsDBCommon.h`
- `0x18000bda1`: `OneCoreUap\Internal\Shell\inc\SettingsDBCommon.h`

## pseudocode

```c
__int64 __fastcall GetSetting(HSTRING string, _QWORD *a2)
{
  PCWSTR StringRawBuffer; // r11
  wchar_t **v5; // r8
  wchar_t *v6; // r9
  _WORD *v7; // rcx
  wchar_t *v8; // rdx
  wchar_t *v9; // rcx
  int v10; // ebx
  const char *v11; // rax
  __int64 v12; // rcx
  const char *v13; // rax
  wil::details::in1diag3 *retaddr; // [rsp+38h] [rbp+0h]
  UINT32 v16; // [rsp+48h] [rbp+10h] BYREF
  __int64 v17; // [rsp+50h] [rbp+18h] BYREF

  *a2 = 0;
  v16 = 0;
  StringRawBuffer = WindowsGetStringRawBuffer(string, &v16);
  v5 = &off_1800521D8;
  while ( 1 )
  {
    v6 = v5[1];
    if ( (wchar_t *)v16 == v6 )
      break;
LABEL_6:
    v5 += 3;
    if ( v5 == (wchar_t **)&g_PitrDll )
      goto LABEL_7;
  }
  v7 = &StringRawBuffer[v16];
  v8 = &(*v5)[(_QWORD)v6];
  while ( v7 != StringRawBuffer )
  {
    if ( *--v7 != *--v8 )
      goto LABEL_6;
  }
LABEL_7:
  if ( v5 == (wchar_t **)&g_PitrDll )
  {
    v13 = (const char *)WindowsGetStringRawBuffer(string, 0);
    v10 = -2147024809;
    wil::details::in1diag3::Return_HrMsg(
      retaddr,
      (void *)0xDC,
      (unsigned int)"OneCoreUap\\Internal\\Shell\\inc\\SettingsDBCommon.h",
      (const char *)0x80070057LL,
      (int)"%ls",
      v13);
  }
  else
  {
    v9 = v5[2];
    v17 = 0;
    v10 = (*(__int64 (__fastcall **)(wchar_t *, __int64 *))(*((_QWORD *)v9 + 5) + 8LL))(v9, &v17);
    if ( v10 >= 0 )
    {
      *a2 = v17;
      return 0;
    }
    else
    {
      v11 = (const char *)WindowsGetStringRawBuffer(string, 0);
      wil::details::in1diag3::Return_HrMsg(
        retaddr,
        (void *)0xE1,
        (unsigned int)"OneCoreUap\\Internal\\Shell\\inc\\SettingsDBCommon.h",
        (const char *)(unsigned int)v10,
        (int)"%ls",
        v11);
      v12 = v17;
      if ( v17 )
      {
        v17 = 0;
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v12 + 16LL))(v12);
      }
    }
  }
  return (unsigned int)v10;
}

```

## disassembly

```asm
0x18000bc70  mov     rax, rsp
0x18000bc73  mov     [rax+8], rbx
0x18000bc77  mov     [rax+20h], rsi
0x18000bc7b  push    rdi
0x18000bc7c  sub     rsp, 30h
0x18000bc80  mov     rdi, rdx
0x18000bc83  mov     rsi, rcx
0x18000bc86  mov     qword ptr [rdx], 0
0x18000bc8d  mov     dword ptr [rax+10h], 0
0x18000bc94  lea     rdx, [rax+10h]; length
0x18000bc98  call    cs:__imp_WindowsGetStringRawBuffer
0x18000bc9e  mov     r11, rax
0x18000bca1  lea     r8, off_1800521D8; "SystemSettings_Misc_PointInTimeRestore_"...
0x18000bca8  mov     r10d, [rsp+38h+arg_8]
0x18000bcad  lea     rbx, ?g_PitrDll@@3VCAutoFreeLibrary@RAII@@A; RAII::CAutoFreeLibrary g_PitrDll
0x18000bcb4  mov     r9, [r8+8]
0x18000bcb8  cmp     r10, r9
0x18000bcbb  jnz     short loc_18000BCDD
0x18000bcbd  lea     rcx, [r11+r10*2]
0x18000bcc1  mov     rdx, [r8]
0x18000bcc4  lea     rdx, [rdx+r9*2]
0x18000bcc8  cmp     rcx, r11
0x18000bccb  jz      short loc_18000BCE6
0x18000bccd  add     rdx, 0FFFFFFFFFFFFFFFEh
0x18000bcd1  add     rcx, 0FFFFFFFFFFFFFFFEh
0x18000bcd5  movzx   eax, word ptr [rdx]
0x18000bcd8  cmp     [rcx], ax
0x18000bcdb  jz      short loc_18000BCC8
0x18000bcdd  add     r8, 18h
0x18000bce1  cmp     r8, rbx
0x18000bce4  jnz     short loc_18000BCB4
0x18000bce6  cmp     r8, rbx
0x18000bce9  jz      loc_18000BD78
0x18000bcef  mov     rcx, [r8+10h]
0x18000bcf3  mov     [rsp+38h+arg_10], 0
0x18000bcfc  mov     rax, [rcx+28h]
0x18000bd00  lea     rdx, [rsp+38h+arg_10]
0x18000bd05  mov     rax, [rax+8]
0x18000bd09  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000bd0e  mov     ebx, eax
0x18000bd10  test    eax, eax
0x18000bd12  jns     short loc_18000BD6C
0x18000bd14  xor     edx, edx; length
0x18000bd16  mov     rcx, rsi; string
0x18000bd19  call    cs:__imp_WindowsGetStringRawBuffer
0x18000bd1f  mov     rcx, [rsp+38h]; this
0x18000bd24  mov     [rsp+38h+var_10], rax; char *
0x18000bd29  lea     rax, aLs; "%ls"
0x18000bd30  mov     qword ptr [rsp+38h+var_18], rax; int
0x18000bd35  mov     r9d, ebx; char *
0x18000bd38  lea     r8, aOnecoreuapInte; "OneCoreUap\\Internal\\Shell\\inc\\Setti"...
0x18000bd3f  mov     edx, 0E1h; void *
0x18000bd44  call    ?Return_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Return_HrMsg(void *,uint,char const *,long,char const *,...)
0x18000bd49  nop
0x18000bd4a  mov     rcx, [rsp+38h+arg_10]
0x18000bd4f  test    rcx, rcx
0x18000bd52  jz      short loc_18000BD6A
0x18000bd54  mov     [rsp+38h+arg_10], 0
0x18000bd5d  mov     rax, [rcx]
0x18000bd60  mov     rax, [rax+10h]
0x18000bd64  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000bd69  nop
0x18000bd6a  jmp     short loc_18000BDB2
0x18000bd6c  mov     rax, [rsp+38h+arg_10]
0x18000bd71  mov     [rdi], rax
0x18000bd74  xor     ebx, ebx
0x18000bd76  jmp     short loc_18000BDB2
0x18000bd78  xor     edx, edx; length
0x18000bd7a  mov     rcx, rsi; string
0x18000bd7d  call    cs:__imp_WindowsGetStringRawBuffer
0x18000bd83  mov     rcx, [rsp+38h]; this
0x18000bd88  mov     [rsp+38h+var_10], rax; char *
0x18000bd8d  lea     rax, aLs; "%ls"
0x18000bd94  mov     qword ptr [rsp+38h+var_18], rax; int
0x18000bd99  mov     ebx, 80070057h
0x18000bd9e  mov     r9d, ebx; char *
0x18000bda1  lea     r8, aOnecoreuapInte; "OneCoreUap\\Internal\\Shell\\inc\\Setti"...
0x18000bda8  mov     edx, 0DCh; void *
0x18000bdad  call    ?Return_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Return_HrMsg(void *,uint,char const *,long,char const *,...)
0x18000bdb2  mov     eax, ebx
0x18000bdb4  mov     rbx, [rsp+38h+arg_0]
0x18000bdb9  mov     rsi, [rsp+38h+arg_18]
0x18000bdbe  add     rsp, 30h
0x18000bdc2  pop     rdi
0x18000bdc3  retn
```
