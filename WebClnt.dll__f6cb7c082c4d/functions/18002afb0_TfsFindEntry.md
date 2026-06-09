# TfsFindEntry

- ea: `0x18002afb0`
- end: `0x18002b0ed`
- name: `TfsFindEntry`
- size: `317`
- prototype: `__int64 __fastcall(__int64, const wchar_t *, _QWORD *)`
- caller_count: `10`
- callee_count: `6`
- tags: ``

## callers

- `0x18002a7d4`
- `0x18002a964`
- `0x18002ae00`
- `0x18002b3bc`
- `0x18002bb70`
- `0x18002bce0`
- `0x18002be24`
- `0x18002c448`
- `0x18002c58c`
- `0x18002c6d0`

## callees

- `0x18000b99c`
- `0x18002afb0`
- `0x18002b5f4`
- `0x18002ca0c`
- `0x18002cf62`
- `0x18002cfa0`

## import_xrefs

- `msvcrt!_wcsicmp` at `0x18002b022`
- `msvcrt!_wcsicmp` at `0x18002b022`
- `KERNEL32!FindFirstFileW` at `0x18002b047`
- `KERNEL32!FindFirstFileW` at `0x18002b047`
- `KERNEL32!FindClose` at `0x18002b097`
- `KERNEL32!FindClose` at `0x18002b097`

## pseudocode

```c
__int64 __fastcall TfsFindEntry(__int64 a1, const wchar_t *a2, _QWORD *a3)
{
  _QWORD *v6; // rdi
  _QWORD *v7; // rbx
  HANDLE FirstFileW; // rax
  int v9; // edx
  int v10; // r8d
  _WIN32_FIND_DATAW FindFileData; // [rsp+30h] [rbp-288h] BYREF

  if ( !a1 )
    return 6;
  *a3 = 0;
  v6 = (_QWORD *)(a1 + 16 * ((unsigned int)TfsGetHashId(a2) + 6LL));
  v7 = (_QWORD *)*v6;
  if ( (_QWORD *)*v6 == v6 )
    return 0;
  while ( *((_DWORD *)v7 + 6) == 2 || _wcsicmp((const wchar_t *)v7[4], a2) )
  {
LABEL_10:
    v7 = (_QWORD *)*v7;
    if ( v7 == v6 )
      return 0;
  }
  memset_0(&FindFileData, 0, sizeof(FindFileData));
  FirstFileW = FindFirstFileW((LPCWSTR)v7[6], &FindFileData);
  if ( FirstFileW == (HANDLE)-1LL )
  {
    *((_DWORD *)v7 + 6) = 2;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_Sd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        33,
        (unsigned int)WPP_5f1a3cf1cc213e2c9d1db611a3b6a3c0_Traceguids,
        v7[6],
        *((_DWORD *)v7 + 5));
    goto LABEL_10;
  }
  FindClose(FirstFileW);
  *a3 = v7;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
    WPP_SF_Sdd(*((_QWORD *)WPP_GLOBAL_Control + 2), v9, v10, v7[6], *((_DWORD *)v7 + 5), *((_DWORD *)v7 + 6));
  return 0;
}

```

## disassembly

```asm
0x18002afb0  push    rbx
0x18002afb2  push    rbp
0x18002afb3  push    rsi
0x18002afb4  push    rdi
0x18002afb5  push    r14
0x18002afb7  sub     rsp, 290h
0x18002afbe  mov     rax, cs:__security_cookie
0x18002afc5  xor     rax, rsp
0x18002afc8  mov     [rsp+2B8h+var_38], rax
0x18002afd0  mov     rsi, r8
0x18002afd3  mov     rbp, rdx
0x18002afd6  mov     rbx, rcx
0x18002afd9  test    rcx, rcx
0x18002afdc  jnz     short loc_18002AFE6
0x18002afde  lea     eax, [rcx+6]
0x18002afe1  jmp     loc_18002B0CF
0x18002afe6  mov     rcx, rbp
0x18002afe9  mov     qword ptr [r8], 0
0x18002aff0  call    TfsGetHashId
0x18002aff5  mov     edi, eax
0x18002aff7  add     rdi, 6
0x18002affb  shl     rdi, 4
0x18002afff  add     rdi, rbx
0x18002b002  mov     rbx, [rdi]
0x18002b005  cmp     rbx, rdi
0x18002b008  jz      loc_18002B0CD
0x18002b00e  lea     r14, WPP_GLOBAL_Control
0x18002b015  cmp     dword ptr [rbx+18h], 2
0x18002b019  jz      short loc_18002B08A
0x18002b01b  mov     rcx, [rbx+20h]; String1
0x18002b01f  mov     rdx, rbp; String2
0x18002b022  call    cs:__imp__wcsicmp
0x18002b028  test    eax, eax
0x18002b02a  jnz     short loc_18002B08A
0x18002b02c  xor     edx, edx; Val
0x18002b02e  lea     rcx, [rsp+2B8h+FindFileData]; void *
0x18002b033  mov     r8d, 250h; Size
0x18002b039  call    memset_0
0x18002b03e  mov     rcx, [rbx+30h]; lpFileName
0x18002b042  lea     rdx, [rsp+2B8h+FindFileData]; lpFindFileData
0x18002b047  call    cs:__imp_FindFirstFileW
0x18002b04d  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18002b051  jnz     short loc_18002B094
0x18002b053  mov     dword ptr [rbx+18h], 2
0x18002b05a  mov     rcx, cs:WPP_GLOBAL_Control
0x18002b061  cmp     rcx, r14
0x18002b064  jz      short loc_18002B08A
0x18002b066  test    byte ptr [rcx+1Ch], 1
0x18002b06a  jz      short loc_18002B08A
0x18002b06c  mov     r9, [rbx+30h]
0x18002b070  lea     edx, [rax+22h]
0x18002b073  mov     eax, [rbx+14h]
0x18002b076  lea     r8, WPP_5f1a3cf1cc213e2c9d1db611a3b6a3c0_Traceguids
0x18002b07d  mov     rcx, [rcx+10h]
0x18002b081  mov     [rsp+2B8h+var_298], eax
0x18002b085  call    WPP_SF_Sd
0x18002b08a  mov     rbx, [rbx]
0x18002b08d  cmp     rbx, rdi
0x18002b090  jnz     short loc_18002B015
0x18002b092  jmp     short loc_18002B0CD
0x18002b094  mov     rcx, rax; hFindFile
0x18002b097  call    cs:__imp_FindClose
0x18002b09d  mov     [rsi], rbx
0x18002b0a0  mov     rcx, cs:WPP_GLOBAL_Control
0x18002b0a7  cmp     rcx, r14
0x18002b0aa  jz      short loc_18002B0CD
0x18002b0ac  test    byte ptr [rcx+1Ch], 2
0x18002b0b0  jz      short loc_18002B0CD
0x18002b0b2  mov     eax, [rbx+18h]
0x18002b0b5  mov     r9, [rbx+30h]
0x18002b0b9  mov     rcx, [rcx+10h]
0x18002b0bd  mov     [rsp+2B8h+var_290], eax
0x18002b0c1  mov     eax, [rbx+14h]
0x18002b0c4  mov     [rsp+2B8h+var_298], eax
0x18002b0c8  call    WPP_SF_Sdd
0x18002b0cd  xor     eax, eax
0x18002b0cf  mov     rcx, [rsp+2B8h+var_38]
0x18002b0d7  xor     rcx, rsp; StackCookie
0x18002b0da  call    __security_check_cookie
0x18002b0df  add     rsp, 290h
0x18002b0e6  pop     r14
0x18002b0e8  pop     rdi
0x18002b0e9  pop     rsi
0x18002b0ea  pop     rbp
0x18002b0eb  pop     rbx
0x18002b0ec  retn
```
