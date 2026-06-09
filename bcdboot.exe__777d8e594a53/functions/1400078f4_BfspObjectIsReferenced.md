# BfspObjectIsReferenced

- ea: `0x1400078f4`
- end: `0x140007c09`
- name: `BfspObjectIsReferenced`
- size: `789`
- prototype: `__int64 __fastcall(__int64, _QWORD *, int, __int64, unsigned int, _BYTE *)`
- caller_count: `2`
- callee_count: `7`
- tags: ``

## callers

- `0x140004828`
- `0x140007e20`

## callees

- `0x1400064c0`
- `0x140006a14`
- `0x140006b08`
- `0x1400078f4`
- `0x14000e628`
- `0x140013b48`
- `0x140013ee8`

## import_xrefs

- `KERNEL32!HeapFree` at `0x140007ac7`
- `KERNEL32!HeapFree` at `0x140007b88`
- `KERNEL32!HeapFree` at `0x140007bb1`
- `KERNEL32!HeapFree` at `0x140007bcf`
- `KERNEL32!HeapFree` at `0x140007ac7`
- `KERNEL32!HeapFree` at `0x140007b88`
- `KERNEL32!HeapFree` at `0x140007bb1`
- `KERNEL32!HeapFree` at `0x140007bcf`
- `KERNEL32!HeapAlloc` at `0x1400079c3`
- `KERNEL32!HeapAlloc` at `0x1400079c3`
- `KERNEL32!GetProcessHeap` at `0x1400079b1`
- `KERNEL32!GetProcessHeap` at `0x140007ab9`
- `KERNEL32!GetProcessHeap` at `0x140007b7a`
- `KERNEL32!GetProcessHeap` at `0x140007ba3`
- `KERNEL32!GetProcessHeap` at `0x140007bc1`
- `KERNEL32!GetProcessHeap` at `0x1400079b1`
- `KERNEL32!GetProcessHeap` at `0x140007ab9`
- `KERNEL32!GetProcessHeap` at `0x140007b7a`
- `KERNEL32!GetProcessHeap` at `0x140007ba3`
- `KERNEL32!GetProcessHeap` at `0x140007bc1`

## string_xrefs

- `0x140007969`: `Failed to open a handle to the bootmgr. Status = [%x]`

## pseudocode

```c
__int64 __fastcall BfspObjectIsReferenced(__int64 a1, _QWORD *a2, int a3, __int64 a4, unsigned int a5, _BYTE *a6)
{
  _QWORD *v7; // r13
  __int64 *v8; // r12
  int v9; // eax
  int IsReferenced; // ebx
  int BcdElementData; // eax
  _DWORD *v12; // r14
  unsigned int v13; // esi
  __int64 v14; // rbx
  HANDLE ProcessHeap; // rax
  __int64 v16; // rdi
  __int64 v17; // rcx
  unsigned int v18; // esi
  unsigned int i; // edx
  __int64 v20; // rsi
  int v21; // eax
  unsigned int v22; // ecx
  HANDLE v23; // rax
  int v24; // eax
  unsigned int v25; // r15d
  __int64 v26; // rdi
  HANDLE v27; // rax
  HANDLE v28; // rax
  HANDLE v29; // rax
  unsigned int v31; // [rsp+30h] [rbp-30h] BYREF
  unsigned int v32; // [rsp+34h] [rbp-2Ch] BYREF
  LPVOID lpMem; // [rsp+38h] [rbp-28h] BYREF
  HANDLE Handle; // [rsp+40h] [rbp-20h] BYREF
  __int64 v35; // [rsp+48h] [rbp-18h] BYREF
  _QWORD *v36; // [rsp+50h] [rbp-10h] BYREF

  v35 = 0;
  v7 = 0;
  v31 = 0;
  v36 = 0;
  v32 = 0;
  Handle = 0;
  v8 = ReferenceElementsBootmgr;
  lpMem = 0;
  v9 = BcdOpenObject(a1, &GUID_WINDOWS_BOOTMGR, &Handle);
  IsReferenced = v9;
  if ( v9 < 0 )
  {
    BfspLogMessage(4, L"Failed to open a handle to the bootmgr. Status = [%x]", (unsigned int)v9);
    goto LABEL_33;
  }
  BcdElementData = BfspGetBcdElementData((__int64)Handle, 0x27000030u, &lpMem, &v31);
  v12 = lpMem;
  IsReferenced = BcdElementData;
  if ( BcdElementData < 0 )
  {
    LODWORD(v16) = 6;
    if ( BcdElementData != -1073741275 )
    {
      BfspLogMessage(4, L"Failed to get bootmgr custom actions. Status = [%x]", (unsigned int)BcdElementData);
      goto LABEL_31;
    }
  }
  else
  {
    v13 = v31;
    v14 = v31 & 0xFFFFFFF8;
    ProcessHeap = GetProcessHeap();
    v8 = (__int64 *)HeapAlloc(ProcessHeap, 8u, v14 + 48);
    if ( !v8 )
    {
      IsReferenced = -1073741801;
      goto LABEL_31;
    }
    LODWORD(v16) = 0;
    v17 = 0;
    do
    {
      v16 = (unsigned int)(v16 + 1);
      *((_DWORD *)v8 + v17) = *((_DWORD *)ReferenceElementsBootmgr + v17);
      ++v17;
    }
    while ( (unsigned int)v16 < 6 );
    v18 = v13 >> 3;
    for ( i = 0; i < v18; ++i )
    {
      if ( HIWORD(v12[4 * i + 1]) == 1 )
      {
        *((_DWORD *)v8 + v16) = v12[4 * i + 2];
        v16 = (unsigned int)(v16 + 1);
      }
    }
  }
  v20 = 0;
  if ( !(_DWORD)v16 )
  {
LABEL_25:
    LODWORD(v35) = 1;
    HIDWORD(v35) = a3 & 0xFFFFF | 0x10200000;
    v24 = BfspEnumerateObjects(a1, (int)&v35, &v32, &v36);
    v7 = v36;
    IsReferenced = v24;
    if ( v24 >= 0 )
    {
      v25 = v32;
      v26 = 0;
      if ( v32 )
      {
        while ( 1 )
        {
          IsReferenced = BfspIdentifierIsReferenced(a1, a2, &v7[3 * v26], a4, a5, a6);
          if ( IsReferenced < 0 || *a6 )
            break;
          v26 = (unsigned int)(v26 + 1);
          if ( (unsigned int)v26 >= v25 )
            goto LABEL_30;
        }
      }
      else
      {
LABEL_30:
        *a6 = 0;
      }
    }
    goto LABEL_31;
  }
  while ( 1 )
  {
    v21 = BfspGetBcdElementData((__int64)Handle, *((_DWORD *)v8 + v20), &lpMem, &v31);
    v12 = lpMem;
    IsReferenced = v21;
    if ( v21 >= 0 )
      break;
    if ( v21 != -1073741275 )
    {
      BfspLogMessage(4, L"Failed to get bootmgr element. Status = [%x]", (unsigned int)v21);
      goto LABEL_31;
    }
LABEL_22:
    if ( lpMem )
    {
      v23 = GetProcessHeap();
      HeapFree(v23, 0, v12);
      v12 = 0;
      v31 = 0;
      lpMem = 0;
    }
    v20 = (unsigned int)(v20 + 1);
    if ( (unsigned int)v20 >= (unsigned int)v16 )
      goto LABEL_25;
  }
  v22 = 0;
  if ( !(v31 >> 4) )
    goto LABEL_22;
  while ( *((_QWORD *)lpMem + 2 * v22) != *a2 || *((_QWORD *)lpMem + 2 * v22 + 1) != a2[1] )
  {
    if ( ++v22 >= v31 >> 4 )
      goto LABEL_22;
  }
  IsReferenced = 0;
  *a6 = 1;
LABEL_31:
  if ( v12 )
  {
    v27 = GetProcessHeap();
    HeapFree(v27, 0, v12);
  }
LABEL_33:
  if ( Handle )
    BcdCloseObject(Handle);
  if ( v7 )
  {
    v28 = GetProcessHeap();
    HeapFree(v28, 0, v7);
  }
  if ( v8 && v8 != ReferenceElementsBootmgr )
  {
    v29 = GetProcessHeap();
    HeapFree(v29, 0, v8);
  }
  return (unsigned int)IsReferenced;
}

```

## disassembly

```asm
0x1400078f4  mov     rax, rsp
0x1400078f7  mov     [rax+18h], rbx
0x1400078fb  mov     [rax+20h], r9
0x1400078ff  mov     [rax+10h], rdx
0x140007903  mov     [rax+8], rcx
0x140007907  push    rbp
0x140007908  push    rsi
0x140007909  push    rdi
0x14000790a  push    r12
0x14000790c  push    r13
0x14000790e  push    r14
0x140007910  push    r15
0x140007912  mov     rbp, rsp
0x140007915  sub     rsp, 60h
0x140007919  mov     r15d, r8d
0x14000791c  mov     [rbp+var_18], 0
0x140007924  xor     r13d, r13d
0x140007927  mov     [rbp+var_30], 0
0x14000792e  lea     rdi, ReferenceElementsBootmgr
0x140007935  mov     [rbp+var_10], r13
0x140007939  lea     r8, [rbp+Handle]
0x14000793d  mov     [rbp+var_2C], r13d
0x140007941  lea     rdx, GUID_WINDOWS_BOOTMGR
0x140007948  mov     [rbp+Handle], 0
0x140007950  mov     r12, rdi
0x140007953  mov     [rbp+lpMem], 0
0x14000795b  call    BcdOpenObject
0x140007960  mov     ebx, eax
0x140007962  test    eax, eax
0x140007964  jns     short loc_14000797E
0x140007966  mov     r8d, eax
0x140007969  lea     rdx, aFailedToOpenAH_1; "Failed to open a handle to the bootmgr."...
0x140007970  lea     ecx, [r13+4]
0x140007974  call    BfspLogMessage
0x140007979  jmp     loc_140007B8E
0x14000797e  mov     rcx, [rbp+Handle]
0x140007982  lea     r9, [rbp+var_30]
0x140007986  lea     r8, [rbp+lpMem]
0x14000798a  mov     edx, 27000030h
0x14000798f  call    BfspGetBcdElementData
0x140007994  mov     r14, [rbp+lpMem]
0x140007998  mov     ebx, eax
0x14000799a  mov     r8d, 1
0x1400079a0  test    eax, eax
0x1400079a2  js      loc_140007A84
0x1400079a8  mov     esi, [rbp+var_30]
0x1400079ab  mov     ebx, esi
0x1400079ad  and     rbx, 0FFFFFFFFFFFFFFF8h
0x1400079b1  call    cs:__imp_GetProcessHeap
0x1400079b7  lea     r8, [rbx+30h]; dwBytes
0x1400079bb  mov     edx, 8; dwFlags
0x1400079c0  mov     rcx, rax; hHeap
0x1400079c3  call    cs:__imp_HeapAlloc
0x1400079c9  mov     r12, rax
0x1400079cc  test    rax, rax
0x1400079cf  jnz     short loc_1400079DB
0x1400079d1  mov     ebx, 0C0000017h
0x1400079d6  jmp     loc_140007B75
0x1400079db  xor     edi, edi
0x1400079dd  lea     rdx, ReferenceElementsBootmgr
0x1400079e4  xor     ecx, ecx
0x1400079e6  lea     r8d, [rdi+1]
0x1400079ea  mov     eax, [rdx+rcx*4]
0x1400079ed  add     edi, r8d
0x1400079f0  mov     [r12+rcx*4], eax
0x1400079f4  add     rcx, r8
0x1400079f7  cmp     edi, 6
0x1400079fa  jb      short loc_1400079EA
0x1400079fc  shr     esi, 3
0x1400079ff  xor     edx, edx
0x140007a01  test    esi, esi
0x140007a03  jz      short loc_140007A25
0x140007a05  mov     eax, edx
0x140007a07  add     rax, rax
0x140007a0a  cmp     [r14+rax*8+6], r8w
0x140007a10  jnz     short loc_140007A1E
0x140007a12  mov     eax, [r14+rax*8+8]
0x140007a17  mov     [r12+rdi*4], eax
0x140007a1b  add     edi, r8d
0x140007a1e  add     edx, r8d
0x140007a21  cmp     edx, esi
0x140007a23  jb      short loc_140007A05
0x140007a25  xor     esi, esi
0x140007a27  test    edi, edi
0x140007a29  jz      loc_140007AE9
0x140007a2f  mov     edx, [r12+rsi*4]
0x140007a33  lea     r9, [rbp+var_30]
0x140007a37  mov     rcx, [rbp+Handle]
0x140007a3b  lea     r8, [rbp+lpMem]
0x140007a3f  call    BfspGetBcdElementData
0x140007a44  mov     r14, [rbp+lpMem]
0x140007a48  mov     ebx, eax
0x140007a4a  test    eax, eax
0x140007a4c  js      short loc_140007AA9
0x140007a4e  mov     edx, [rbp+var_30]
0x140007a51  xor     ecx, ecx
0x140007a53  shr     edx, 4
0x140007a56  test    edx, edx
0x140007a58  jz      short loc_140007AB4
0x140007a5a  mov     r9, [rbp+arg_8]
0x140007a5e  mov     r8d, ecx
0x140007a61  add     r8, r8
0x140007a64  mov     rax, [r14+r8*8]
0x140007a68  cmp     rax, [r9]
0x140007a6b  jnz     short loc_140007A7C
0x140007a6d  mov     rax, [r14+r8*8+8]
0x140007a72  cmp     rax, [r9+8]
0x140007a76  jz      loc_140007BEF
0x140007a7c  inc     ecx
0x140007a7e  cmp     ecx, edx
0x140007a80  jb      short loc_140007A5E
0x140007a82  jmp     short loc_140007AB4
0x140007a84  mov     edi, 6
0x140007a89  cmp     eax, 0C0000225h
0x140007a8e  jz      short loc_140007A25
0x140007a90  lea     rdx, aFailedToGetBoo_0; "Failed to get bootmgr custom actions. S"...
0x140007a97  mov     r8d, eax
0x140007a9a  mov     ecx, 4
0x140007a9f  call    BfspLogMessage
0x140007aa4  jmp     loc_140007B6E
0x140007aa9  cmp     eax, 0C0000225h
0x140007aae  jnz     loc_140007BFD
0x140007ab4  test    r14, r14
0x140007ab7  jz      short loc_140007AD8
0x140007ab9  call    cs:__imp_GetProcessHeap
0x140007abf  mov     r8, r14; lpMem
0x140007ac2  xor     edx, edx; dwFlags
0x140007ac4  mov     rcx, rax; hHeap
0x140007ac7  call    cs:__imp_HeapFree
0x140007acd  xor     r14d, r14d
0x140007ad0  mov     [rbp+var_30], r13d
0x140007ad4  mov     [rbp+lpMem], r14
0x140007ad8  mov     r8d, 1
0x140007ade  add     esi, r8d
0x140007ae1  cmp     esi, edi
0x140007ae3  jb      loc_140007A2F
0x140007ae9  mov     rcx, [rbp+arg_0]
0x140007aed  lea     r9, [rbp+var_10]
0x140007af1  mov     dword ptr [rbp+var_18], r8d
0x140007af5  lea     rdx, [rbp+var_18]
0x140007af9  and     r15d, 0FFFFFh
0x140007b00  lea     r8, [rbp+var_2C]
0x140007b04  or      r15d, 10200000h
0x140007b0b  mov     dword ptr [rbp+var_18+4], r15d
0x140007b0f  call    BfspEnumerateObjects
0x140007b14  mov     r13, [rbp+var_10]
0x140007b18  mov     ebx, eax
0x140007b1a  test    eax, eax
0x140007b1c  js      short loc_140007B6E
0x140007b1e  mov     r15d, [rbp+var_2C]
0x140007b22  xor     edi, edi
0x140007b24  mov     rsi, [rbp+arg_28]
0x140007b28  test    r15d, r15d
0x140007b2b  jz      short loc_140007B6B
0x140007b2d  mov     eax, [rbp+arg_20]
0x140007b30  lea     rcx, [rdi+rdi*2]
0x140007b34  mov     r9, [rbp+arg_18]
0x140007b38  lea     r8, ds:0[rcx*8]
0x140007b40  mov     rdx, [rbp+arg_8]
0x140007b44  add     r8, r13
0x140007b47  mov     rcx, [rbp+arg_0]
0x140007b4b  mov     [rsp+60h+var_38], rsi
0x140007b50  mov     [rsp+60h+var_40], eax
0x140007b54  call    BfspIdentifierIsReferenced
0x140007b59  mov     ebx, eax
0x140007b5b  test    eax, eax
0x140007b5d  js      short loc_140007B6E
0x140007b5f  cmp     byte ptr [rsi], 0
0x140007b62  jnz     short loc_140007B6E
0x140007b64  inc     edi
0x140007b66  cmp     edi, r15d
0x140007b69  jb      short loc_140007B2D
0x140007b6b  mov     byte ptr [rsi], 0
0x140007b6e  lea     rdi, ReferenceElementsBootmgr
0x140007b75  test    r14, r14
0x140007b78  jz      short loc_140007B8E
0x140007b7a  call    cs:__imp_GetProcessHeap
0x140007b80  mov     r8, r14; lpMem
0x140007b83  xor     edx, edx; dwFlags
0x140007b85  mov     rcx, rax; hHeap
0x140007b88  call    cs:__imp_HeapFree
0x140007b8e  cmp     [rbp+Handle], 0
0x140007b93  jz      short loc_140007B9E
0x140007b95  mov     rcx, [rbp+Handle]; Handle
0x140007b99  call    BcdCloseObject
0x140007b9e  test    r13, r13
0x140007ba1  jz      short loc_140007BB7
0x140007ba3  call    cs:__imp_GetProcessHeap
0x140007ba9  mov     r8, r13; lpMem
0x140007bac  xor     edx, edx; dwFlags
0x140007bae  mov     rcx, rax; hHeap
0x140007bb1  call    cs:__imp_HeapFree
0x140007bb7  test    r12, r12
0x140007bba  jz      short loc_140007BD5
0x140007bbc  cmp     r12, rdi
0x140007bbf  jz      short loc_140007BD5
0x140007bc1  call    cs:__imp_GetProcessHeap
0x140007bc7  mov     r8, r12; lpMem
0x140007bca  xor     edx, edx; dwFlags
0x140007bcc  mov     rcx, rax; hHeap
0x140007bcf  call    cs:__imp_HeapFree
0x140007bd5  mov     eax, ebx
0x140007bd7  mov     rbx, [rsp+60h+arg_10]
0x140007bdf  add     rsp, 60h
0x140007be3  pop     r15
0x140007be5  pop     r14
0x140007be7  pop     r13
0x140007be9  pop     r12
0x140007beb  pop     rdi
0x140007bec  pop     rsi
0x140007bed  pop     rbp
0x140007bee  retn
0x140007bef  mov     rax, [rbp+arg_28]
0x140007bf3  xor     ebx, ebx
0x140007bf5  mov     byte ptr [rax], 1
0x140007bf8  jmp     loc_140007B6E
0x140007bfd  lea     rdx, aFailedToGetBoo; "Failed to get bootmgr element. Status ="...
0x140007c04  jmp     loc_140007A97
```
