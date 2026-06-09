# winreRecoveryBCDHasEntry(void *,int *)

- ea: `0x1800341a0`
- end: `0x1800342ed`
- name: `?winreRecoveryBCDHasEntry@@YAKPEAXPEAH@Z`
- size: `333`
- prototype: `unsigned int __fastcall(void *, int *)`
- caller_count: `2`
- callee_count: `4`
- tags: `loader_planting`

## callers

- `0x1800356d4`
- `0x1800361ac`

## callees

- `0x1800059fc`
- `0x1800341a0`
- `0x18005ced6`
- `0x18005cf30`

## import_xrefs

- `ntdll!RtlNtStatusToDosError` at `0x180034209`
- `ntdll!RtlNtStatusToDosError` at `0x180034209`
- `bcd!BcdCloseObject` at `0x1800342c9`
- `bcd!BcdCloseObject` at `0x1800342c9`
- `bcd!BcdGetElementData` at `0x180034230`
- `bcd!BcdGetElementData` at `0x180034263`
- `bcd!BcdGetElementData` at `0x180034230`
- `bcd!BcdGetElementData` at `0x180034263`
- `bcd!BcdOpenObject` at `0x1800341e7`
- `bcd!BcdOpenObject` at `0x1800341e7`

## string_xrefs

- `0x1800341f3`: `Failed to open bootmgr in Recovery BCD: 0x%x`
- `0x180034289`: `Unable to read display order: 0x%x`

## pseudocode

```c
__int64 __fastcall winreRecoveryBCDHasEntry(void *a1, int *a2)
{
  NTSTATUS v3; // ebx
  ULONG v4; // edi
  int ElementData; // eax
  unsigned int v6; // eax
  BOOL v7; // ecx
  __int64 v9; // [rsp+20h] [rbp-30h] BYREF
  unsigned int v10; // [rsp+28h] [rbp-28h] BYREF
  __int128 Buf1; // [rsp+30h] [rbp-20h] BYREF

  *a2 = 0;
  v9 = 0;
  v10 = 0;
  Buf1 = 0;
  v3 = BcdOpenObject(a1, &GUID_WINDOWS_BOOTMGR, &v9);
  if ( v3 < 0 )
  {
    UnattendLogW(1, L"Failed to open bootmgr in Recovery BCD: 0x%x", (unsigned int)v3);
LABEL_3:
    v4 = RtlNtStatusToDosError(v3);
    goto LABEL_15;
  }
  v10 = 16;
  v4 = 0;
  ElementData = BcdGetElementData(v9, 587202563, &Buf1, &v10);
  if ( ElementData < 0 )
  {
    UnattendLogW(
      0,
      L"Unable to get default BCD object (0x%x), checking display order instead",
      (unsigned int)ElementData);
    v10 = 16;
    v6 = BcdGetElementData(v9, 603979777, &Buf1, &v10);
    v3 = v6;
    if ( v6 == -1073741275 )
    {
      *a2 = 0;
      goto LABEL_15;
    }
    if ( (int)(v6 + 0x80000000) >= 0 && v6 != -1073741789 )
    {
      UnattendLogW(1, L"Unable to read display order: 0x%x", v6);
      goto LABEL_3;
    }
  }
  v7 = v10 >= 0x10 && memcmp_0(&Buf1, &GUID_NULL, 0x10u);
  *a2 = v7;
LABEL_15:
  if ( v9 )
    BcdCloseObject();
  return v4;
}

```

## disassembly

```asm
0x1800341a0  mov     [rsp-18h+arg_10], rbx
0x1800341a5  push    rbp
0x1800341a6  push    rsi
0x1800341a7  push    rdi
0x1800341a8  mov     rbp, rsp
0x1800341ab  sub     rsp, 50h
0x1800341af  mov     rax, cs:__security_cookie
0x1800341b6  xor     rax, rsp
0x1800341b9  mov     [rbp+var_10], rax
0x1800341bd  mov     rsi, rdx
0x1800341c0  mov     dword ptr [rdx], 0
0x1800341c6  xorps   xmm0, xmm0
0x1800341c9  mov     [rbp+var_30], 0
0x1800341d1  lea     rdx, GUID_WINDOWS_BOOTMGR
0x1800341d8  mov     [rbp+var_28], 0
0x1800341df  lea     r8, [rbp+var_30]
0x1800341e3  movups  [rbp+Buf1], xmm0
0x1800341e7  call    cs:__imp_BcdOpenObject
0x1800341ed  mov     ebx, eax
0x1800341ef  test    eax, eax
0x1800341f1  jns     short loc_180034216
0x1800341f3  lea     rdx, aFailedToOpenBo; "Failed to open bootmgr in Recovery BCD:"...
0x1800341fa  mov     r8d, ebx
0x1800341fd  mov     ecx, 1
0x180034202  call    UnattendLogW
0x180034207  mov     ecx, ebx; Status
0x180034209  call    cs:__imp_RtlNtStatusToDosError
0x18003420f  mov     edi, eax
0x180034211  jmp     loc_1800342C0
0x180034216  mov     rcx, [rbp+var_30]
0x18003421a  lea     r9, [rbp+var_28]
0x18003421e  lea     r8, [rbp+Buf1]
0x180034222  mov     [rbp+var_28], 10h
0x180034229  mov     edx, 23000003h
0x18003422e  xor     edi, edi
0x180034230  call    cs:__imp_BcdGetElementData
0x180034236  test    eax, eax
0x180034238  jns     short loc_180034295
0x18003423a  mov     r8d, eax
0x18003423d  lea     rdx, aUnableToGetDef; "Unable to get default BCD object (0x%x)"...
0x180034244  xor     ecx, ecx
0x180034246  call    UnattendLogW
0x18003424b  mov     rcx, [rbp+var_30]
0x18003424f  lea     r9, [rbp+var_28]
0x180034253  lea     r8, [rbp+Buf1]
0x180034257  mov     [rbp+var_28], 10h
0x18003425e  mov     edx, 24000001h
0x180034263  call    cs:__imp_BcdGetElementData
0x180034269  mov     ebx, eax
0x18003426b  cmp     eax, 0C0000225h
0x180034270  jnz     short loc_180034276
0x180034272  mov     [rsi], edi
0x180034274  jmp     short loc_1800342C0
0x180034276  mov     ecx, 80000000h
0x18003427b  add     eax, ecx
0x18003427d  test    ecx, eax
0x18003427f  jnz     short loc_180034295
0x180034281  cmp     ebx, 0C0000023h
0x180034287  jz      short loc_180034295
0x180034289  lea     rdx, aUnableToReadDi; "Unable to read display order: 0x%x"
0x180034290  jmp     loc_1800341FA
0x180034295  cmp     [rbp+var_28], 10h
0x180034299  jb      short loc_1800342BC
0x18003429b  mov     r8d, 10h; Size
0x1800342a1  lea     rdx, GUID_NULL; Buf2
0x1800342a8  lea     rcx, [rbp+Buf1]; Buf1
0x1800342ac  call    memcmp_0
0x1800342b1  test    eax, eax
0x1800342b3  jz      short loc_1800342BC
0x1800342b5  mov     ecx, 1
0x1800342ba  jmp     short loc_1800342BE
0x1800342bc  xor     ecx, ecx
0x1800342be  mov     [rsi], ecx
0x1800342c0  mov     rcx, [rbp+var_30]
0x1800342c4  test    rcx, rcx
0x1800342c7  jz      short loc_1800342CF
0x1800342c9  call    cs:__imp_BcdCloseObject
0x1800342cf  mov     eax, edi
0x1800342d1  mov     rcx, [rbp+var_10]
0x1800342d5  xor     rcx, rsp; StackCookie
0x1800342d8  call    __security_check_cookie
0x1800342dd  mov     rbx, [rsp+50h+arg_10]
0x1800342e5  add     rsp, 50h
0x1800342e9  pop     rdi
0x1800342ea  pop     rsi
0x1800342eb  pop     rbp
0x1800342ec  retn
```
