# DavWriteRawCallback

- ea: `0x18001bfe0`
- end: `0x18001c0c8`
- name: `DavWriteRawCallback`
- size: `232`
- prototype: `__int64 __fastcall(PBYTE pbData, PVOID pvCallbackContext, PULONG ulLength)`
- caller_count: `0`
- callee_count: `2`
- tags: `file_ops`

## callees

- `0x18000b7dc`
- `0x18001bfe0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001c04f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001c04f`
- `api-ms-win-core-file-l1-1-0!ReadFile` at `0x18001c045`
- `api-ms-win-core-file-l1-1-0!ReadFile` at `0x18001c045`

## pseudocode

```c
__int64 __fastcall DavWriteRawCallback(PBYTE pbData, PVOID pvCallbackContext, PULONG ulLength)
{
  DWORD v3; // ebx
  DWORD LastError; // eax
  _QWORD *v8; // rcx
  DWORD NumberOfBytesRead; // [rsp+60h] [rbp+18h] BYREF

  v3 = 0;
  NumberOfBytesRead = 0;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 227, WPP_03a38b450eb239675e3775cc0b0f525c_Traceguids, *ulLength);
  if ( ReadFile(pvCallbackContext, pbData, *ulLength, &NumberOfBytesRead, 0) )
    goto LABEL_8;
  LastError = GetLastError();
  v3 = LastError;
  v8 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control )
    goto LABEL_12;
  if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
  {
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 228, WPP_03a38b450eb239675e3775cc0b0f525c_Traceguids, LastError);
LABEL_8:
    v8 = WPP_GLOBAL_Control;
  }
  if ( v8 != &WPP_GLOBAL_Control && (*((_BYTE *)v8 + 28) & 2) != 0 )
    WPP_SF_d(v8[2], 229, WPP_03a38b450eb239675e3775cc0b0f525c_Traceguids, NumberOfBytesRead);
LABEL_12:
  *ulLength = NumberOfBytesRead;
  return v3;
}

```

## disassembly

```asm
0x18001bfe0  mov     [rsp+arg_0], rbx
0x18001bfe5  mov     [rsp+arg_8], rbp
0x18001bfea  push    rsi
0x18001bfeb  push    rdi
0x18001bfec  push    r14
0x18001bfee  sub     rsp, 30h
0x18001bff2  xor     ebx, ebx
0x18001bff4  mov     rdi, r8
0x18001bff7  mov     [rsp+48h+NumberOfBytesRead], ebx
0x18001bffb  mov     rsi, rdx
0x18001bffe  mov     rbp, rcx
0x18001c001  mov     rcx, cs:WPP_GLOBAL_Control
0x18001c008  lea     r14, WPP_GLOBAL_Control
0x18001c00f  cmp     rcx, r14
0x18001c012  jz      short loc_18001C032
0x18001c014  test    byte ptr [rcx+1Ch], 2
0x18001c018  jz      short loc_18001C032
0x18001c01a  mov     r9d, [r8]
0x18001c01d  mov     edx, 0E3h
0x18001c022  mov     rcx, [rcx+10h]
0x18001c026  lea     r8, WPP_03a38b450eb239675e3775cc0b0f525c_Traceguids
0x18001c02d  call    WPP_SF_d
0x18001c032  mov     r8d, [rdi]; nNumberOfBytesToRead
0x18001c035  lea     r9, [rsp+48h+NumberOfBytesRead]; lpNumberOfBytesRead
0x18001c03a  mov     rdx, rbp; lpBuffer
0x18001c03d  mov     [rsp+48h+lpOverlapped], rbx; lpOverlapped
0x18001c042  mov     rcx, rsi; hFile
0x18001c045  call    cs:__imp_ReadFile
0x18001c04b  test    eax, eax
0x18001c04d  jnz     short loc_18001C081
0x18001c04f  call    cs:__imp_GetLastError
0x18001c055  mov     ebx, eax
0x18001c057  mov     rcx, cs:WPP_GLOBAL_Control
0x18001c05e  cmp     rcx, r14
0x18001c061  jz      short loc_18001C0AD
0x18001c063  test    byte ptr [rcx+1Ch], 1
0x18001c067  jz      short loc_18001C088
0x18001c069  mov     rcx, [rcx+10h]
0x18001c06d  lea     r8, WPP_03a38b450eb239675e3775cc0b0f525c_Traceguids
0x18001c074  mov     edx, 0E4h
0x18001c079  mov     r9d, eax
0x18001c07c  call    WPP_SF_d
0x18001c081  mov     rcx, cs:WPP_GLOBAL_Control
0x18001c088  cmp     rcx, r14
0x18001c08b  jz      short loc_18001C0AD
0x18001c08d  test    byte ptr [rcx+1Ch], 2
0x18001c091  jz      short loc_18001C0AD
0x18001c093  mov     r9d, [rsp+48h+NumberOfBytesRead]
0x18001c098  lea     r8, WPP_03a38b450eb239675e3775cc0b0f525c_Traceguids
0x18001c09f  mov     rcx, [rcx+10h]
0x18001c0a3  mov     edx, 0E5h
0x18001c0a8  call    WPP_SF_d
0x18001c0ad  mov     eax, [rsp+48h+NumberOfBytesRead]
0x18001c0b1  mov     rbp, [rsp+48h+arg_8]
0x18001c0b6  mov     [rdi], eax
0x18001c0b8  mov     eax, ebx
0x18001c0ba  mov     rbx, [rsp+48h+arg_0]
0x18001c0bf  add     rsp, 30h
0x18001c0c3  pop     r14
0x18001c0c5  pop     rdi
0x18001c0c6  pop     rsi
0x18001c0c7  retn
```
