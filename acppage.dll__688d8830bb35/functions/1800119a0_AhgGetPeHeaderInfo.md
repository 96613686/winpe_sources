# AhgGetPeHeaderInfo

- ea: `0x1800119a0`
- end: `0x180011b21`
- name: `AhgGetPeHeaderInfo`
- size: `385`
- prototype: `__int64 __fastcall(_DWORD *, _DWORD *, _DWORD *, _DWORD *, int *, PVOID BaseAddress)`
- caller_count: `1`
- callee_count: `4`
- tags: `loader_planting, service_task`

## callers

- `0x18001123c`

## callees

- `0x1800119a0`
- `0x180011b28`
- `0x180011c2c`
- `0x180015220`

## import_xrefs

- `msvcrt!sscanf_s` at `0x180011ad7`
- `msvcrt!sscanf_s` at `0x180011ad7`
- `ntdll!RtlImageDirectoryEntryToData` at `0x180011a9b`
- `ntdll!RtlImageDirectoryEntryToData` at `0x180011a9b`
- `ntdll!RtlImageRvaToVa` at `0x180011ab9`
- `ntdll!RtlImageRvaToVa` at `0x180011ab9`

## string_xrefs

- `0x1800119ef`: `Failed to read PE header. Could be a corrupted image or 16-bit app.`
- `0x180011a25`: `Failed to read TimeDataStampYear in PE header.`

## pseudocode

```c
__int64 __fastcall AhgGetPeHeaderInfo(_DWORD *a1, _DWORD *a2, _DWORD *a3, _DWORD *a4, int *a5, PVOID BaseAddress)
{
  int v6; // ebx
  int v7; // r15d
  int v8; // edi
  int v9; // r13d
  __int64 v10; // rax
  __int64 v11; // r14
  unsigned int TimeDateStampYear; // esi
  unsigned int v13; // r13d
  _DWORD *v14; // rax
  const char *v15; // rax
  int v17; // [rsp+20h] [rbp-20h] BYREF
  int v18; // [rsp+24h] [rbp-1Ch]
  int v19; // [rsp+28h] [rbp-18h]
  int v20; // [rsp+2Ch] [rbp-14h] BYREF
  ULONG Size[4]; // [rsp+30h] [rbp-10h] BYREF

  v6 = 0;
  v7 = 0;
  v18 = 0;
  v8 = 0;
  v20 = 0;
  v19 = 0;
  v9 = 0;
  v17 = 0;
  Size[0] = 0;
  v10 = RtlpImageNtHeader(BaseAddress);
  v11 = v10;
  if ( v10 )
  {
    TimeDateStampYear = AhgpGetTimeDateStampYear(&v20, *(unsigned int *)(v10 + 8));
    if ( TimeDateStampYear )
    {
      AslLogCallPrintf(1, "AhgGetPeHeaderInfo", 200, "Failed to read TimeDataStampYear in PE header.");
    }
    else
    {
      v13 = *(unsigned __int16 *)(v11 + 94);
      v7 = v20;
      if ( *(_DWORD *)(v11 + 8) == 708992537 )
        v7 = 0;
      v18 = *(_DWORD *)(v11 + 64);
      v19 = *(_DWORD *)(v11 + 72);
      v9 = (v13 >> 8) & 1;
      v14 = RtlImageDirectoryEntryToData(BaseAddress, 0, 0xEu, Size);
      if ( v14 )
      {
        if ( Size[0] )
        {
          v15 = (const char *)RtlImageRvaToVa((PIMAGE_NT_HEADERS)v11, BaseAddress, v14[2], 0);
          if ( v15 )
          {
            if ( sscanf_s(v15 + 16, "v%hd.%hd", &v17, (char *)&v17 + 2) != 2 )
              v17 = 0;
          }
        }
      }
      v6 = v18;
      TimeDateStampYear = 0;
      v8 = v19;
    }
  }
  else
  {
    AslLogCallPrintf(
      2,
      "AhgGetPeHeaderInfo",
      185,
      "Failed to read PE header. Could be a corrupted image or 16-bit app.");
    TimeDateStampYear = 30;
  }
  *a1 = v7;
  *a2 = v6;
  *a3 = v8;
  *a4 = v17;
  *a5 = v9;
  return TimeDateStampYear;
}

```

## disassembly

```asm
0x1800119a0  mov     rax, rsp
0x1800119a3  mov     [rax+20h], r9
0x1800119a7  mov     [rax+18h], r8
0x1800119ab  mov     [rax+10h], rdx
0x1800119af  mov     [rax+8], rcx
0x1800119b3  push    rbp
0x1800119b4  push    rbx
0x1800119b5  push    rsi
0x1800119b6  push    rdi
0x1800119b7  push    r13
0x1800119b9  push    r14
0x1800119bb  push    r15
0x1800119bd  mov     rbp, rsp
0x1800119c0  sub     rsp, 40h
0x1800119c4  mov     rcx, [rbp+BaseAddress]
0x1800119c8  xor     ebx, ebx
0x1800119ca  xor     r15d, r15d
0x1800119cd  mov     [rbp+var_1C], ebx
0x1800119d0  xor     edi, edi
0x1800119d2  mov     [rbp+var_14], r15d
0x1800119d6  mov     [rbp+var_18], edi
0x1800119d9  xor     r13d, r13d
0x1800119dc  mov     [rbp+var_20], ebx
0x1800119df  mov     [rbp+Size], ebx
0x1800119e2  call    RtlpImageNtHeader
0x1800119e7  mov     r14, rax
0x1800119ea  test    rax, rax
0x1800119ed  jnz     short loc_180011A13
0x1800119ef  lea     r9, aFailedToReadPe_0; "Failed to read PE header. Could be a co"...
0x1800119f6  mov     r8d, 0B9h
0x1800119fc  lea     rdx, aAhggetpeheader; "AhgGetPeHeaderInfo"
0x180011a03  lea     ecx, [rbx+2]
0x180011a06  call    AslLogCallPrintf
0x180011a0b  lea     esi, [rbx+1Eh]
0x180011a0e  jmp     loc_180011AED
0x180011a13  mov     edx, [rax+8]
0x180011a16  lea     rcx, [rbp+var_14]
0x180011a1a  call    AhgpGetTimeDateStampYear
0x180011a1f  mov     esi, eax
0x180011a21  test    eax, eax
0x180011a23  jz      short loc_180011A48
0x180011a25  lea     r9, aFailedToReadTi; "Failed to read TimeDataStampYear in PE "...
0x180011a2c  mov     r8d, 0C8h
0x180011a32  lea     rdx, aAhggetpeheader; "AhgGetPeHeaderInfo"
0x180011a39  mov     ecx, 1
0x180011a3e  call    AslLogCallPrintf
0x180011a43  jmp     loc_180011AED
0x180011a48  movzx   r13d, word ptr [r14+5Eh]
0x180011a4d  lea     r9, [rbp+Size]; Size
0x180011a51  mov     r15d, [rbp+var_14]
0x180011a55  xor     eax, eax
0x180011a57  cmp     dword ptr [r14+8], 2A425E19h
0x180011a5f  mov     r8d, 0Eh; Directory
0x180011a65  mov     rcx, [rbp+BaseAddress]; BaseAddress
0x180011a69  cmovz   r15d, eax
0x180011a6d  movzx   eax, word ptr [r14+40h]
0x180011a72  mov     word ptr [rbp+var_1C], ax
0x180011a76  xor     edx, edx; MappedAsImage
0x180011a78  movzx   eax, word ptr [r14+42h]
0x180011a7d  mov     word ptr [rbp+var_1C+2], ax
0x180011a81  movzx   eax, word ptr [r14+48h]
0x180011a86  mov     word ptr [rbp+var_18], ax
0x180011a8a  movzx   eax, word ptr [r14+4Ah]
0x180011a8f  shr     r13d, 8
0x180011a93  mov     word ptr [rbp+var_18+2], ax
0x180011a97  and     r13d, 1
0x180011a9b  call    cs:__imp_RtlImageDirectoryEntryToData
0x180011aa1  test    rax, rax
0x180011aa4  jz      short loc_180011AE5
0x180011aa6  cmp     [rbp+Size], ebx
0x180011aa9  jz      short loc_180011AE5
0x180011aab  mov     r8d, [rax+8]; Rva
0x180011aaf  xor     r9d, r9d; SectionHeader
0x180011ab2  mov     rdx, [rbp+BaseAddress]; BaseAddress
0x180011ab6  mov     rcx, r14; NtHeader
0x180011ab9  call    cs:__imp_RtlImageRvaToVa
0x180011abf  test    rax, rax
0x180011ac2  jz      short loc_180011AE5
0x180011ac4  lea     rcx, [rax+10h]; Buffer
0x180011ac8  lea     r9, [rbp+var_20+2]
0x180011acc  lea     r8, [rbp+var_20]
0x180011ad0  lea     rdx, Format; "v%hd.%hd"
0x180011ad7  call    cs:__imp_sscanf_s
0x180011add  cmp     eax, 2
0x180011ae0  jz      short loc_180011AE5
0x180011ae2  mov     [rbp+var_20], ebx
0x180011ae5  mov     ebx, [rbp+var_1C]
0x180011ae8  xor     esi, esi
0x180011aea  mov     edi, [rbp+var_18]
0x180011aed  mov     rax, [rbp+arg_0]
0x180011af1  mov     rcx, [rbp+arg_18]
0x180011af5  mov     [rax], r15d
0x180011af8  mov     rax, [rbp+arg_8]
0x180011afc  mov     [rax], ebx
0x180011afe  mov     rax, [rbp+arg_10]
0x180011b02  mov     [rax], edi
0x180011b04  mov     eax, [rbp+var_20]
0x180011b07  mov     [rcx], eax
0x180011b09  mov     rax, [rbp+arg_20]
0x180011b0d  mov     [rax], r13d
0x180011b10  mov     eax, esi
0x180011b12  add     rsp, 40h
0x180011b16  pop     r15
0x180011b18  pop     r14
0x180011b1a  pop     r13
0x180011b1c  pop     rdi
0x180011b1d  pop     rsi
0x180011b1e  pop     rbx
0x180011b1f  pop     rbp
0x180011b20  retn
```
