# WimpFSFIntegrityValidateIntegrityFile

- ea: `0x14002a090`
- end: `0x14002a3db`
- name: `WimpFSFIntegrityValidateIntegrityFile`
- size: `843`
- prototype: `__int64 __fastcall(__int64, struct _FILE_OBJECT *, void *, unsigned __int64, char *, char *, _DWORD *, _QWORD *)`
- caller_count: `2`
- callee_count: `2`
- tags: `file_ops, broker_com_uri`

## callers

- `0x1400284d8`
- `0x140028924`

## callees

- `0x140011560`
- `0x14002a090`

## import_xrefs

- `ntoskrnl!RtlCompareMemory` at `0x14002a27b`
- `ntoskrnl!RtlCompareMemory` at `0x14002a2a8`
- `ntoskrnl!RtlCompareMemory` at `0x14002a27b`
- `ntoskrnl!RtlCompareMemory` at `0x14002a2a8`
- `ntoskrnl!ExFreePoolWithTag` at `0x14002a3a5`
- `ntoskrnl!ExFreePoolWithTag` at `0x14002a3a5`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x14002a173`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x14002a173`
- `FLTMGR!FltReadFile` at `0x14002a1d2`
- `FLTMGR!FltReadFile` at `0x14002a1d2`
- `FLTMGR!FltQueryInformationFile` at `0x14002a317`
- `FLTMGR!FltQueryInformationFile` at `0x14002a317`
- `cng!BCryptCreateHash` at `0x14002a14f`
- `cng!BCryptCreateHash` at `0x14002a14f`
- `cng!BCryptHashData` at `0x14002a232`
- `cng!BCryptHashData` at `0x14002a232`
- `cng!BCryptDestroyHash` at `0x14002a375`
- `cng!BCryptDestroyHash` at `0x14002a375`
- `cng!BCryptCloseAlgorithmProvider` at `0x14002a38c`
- `cng!BCryptCloseAlgorithmProvider` at `0x14002a38c`
- `cng!BCryptFinishHash` at `0x14002a258`
- `cng!BCryptFinishHash` at `0x14002a258`
- `cng!BCryptOpenAlgorithmProvider` at `0x14002a11e`
- `cng!BCryptOpenAlgorithmProvider` at `0x14002a11e`

## pseudocode

```c
__int64 __fastcall WimpFSFIntegrityValidateIntegrityFile(
        __int64 a1,
        struct _FILE_OBJECT *a2,
        void *a3,
        unsigned __int64 a4,
        char *a5,
        char *a6,
        _DWORD *a7,
        _QWORD *a8)
{
  UCHAR *PoolWithTag; // rdi
  NTSTATUS v12; // ebx
  struct _FLT_INSTANCE *v13; // rcx
  int v14; // r12d
  __int64 v15; // rcx
  char v16; // r14
  char v17; // r15
  unsigned __int64 v18; // rax
  unsigned __int64 v19; // rcx
  unsigned __int64 v20; // rsi
  __int64 v22; // [rsp+50h] [rbp-79h]
  ULONG BytesRead; // [rsp+60h] [rbp-69h] BYREF
  BCRYPT_HASH_HANDLE phHash; // [rsp+68h] [rbp-61h] BYREF
  BCRYPT_ALG_HANDLE phAlgorithm; // [rsp+70h] [rbp-59h] BYREF
  union _LARGE_INTEGER ByteOffset; // [rsp+78h] [rbp-51h] BYREF
  void *Source2; // [rsp+80h] [rbp-49h]
  PFILE_OBJECT FileObject; // [rsp+88h] [rbp-41h]
  __int64 v29; // [rsp+90h] [rbp-39h]
  char *v30; // [rsp+98h] [rbp-31h]
  char *v31; // [rsp+A0h] [rbp-29h]
  _DWORD *v32; // [rsp+A8h] [rbp-21h]
  __int128 FileInformation; // [rsp+B0h] [rbp-19h] BYREF
  __int64 v34; // [rsp+C0h] [rbp-9h]

  v31 = a5;
  v30 = a6;
  PoolWithTag = 0;
  v32 = a7;
  Source2 = a3;
  FileObject = a2;
  v29 = a1;
  v34 = 0;
  phAlgorithm = 0;
  phHash = 0;
  ByteOffset.QuadPart = 0;
  BytesRead = 0;
  FileInformation = 0;
  v12 = BCryptOpenAlgorithmProvider(&phAlgorithm, L"SHA256", 0, 0);
  if ( v12 >= 0 )
  {
    v12 = BCryptCreateHash(phAlgorithm, &phHash, 0, 0, 0, 0, 0);
    if ( v12 >= 0 )
    {
      PoolWithTag = (UCHAR *)ExAllocatePoolWithTag(PagedPool, 0x94u, 0x69637077u);
      if ( !PoolWithTag )
      {
        v12 = -1073741801;
        goto LABEL_30;
      }
      v13 = *(struct _FLT_INSTANCE **)(a1 + 120);
      ByteOffset.QuadPart = 0;
      v12 = FltReadFile(v13, a2, &ByteOffset, 0x74u, PoolWithTag, 0, &BytesRead, 0, 0);
      if ( v12 >= 0 )
      {
        if ( BytesRead != 116 )
        {
          v12 = -1073741116;
          goto LABEL_30;
        }
        v14 = 0;
        v15 = 0;
        v16 = 0;
        v17 = 0;
        if ( *(_DWORD *)PoolWithTag == 1766027095
          && *((_DWORD *)PoolWithTag + 1) == 1
          && *((_DWORD *)PoolWithTag + 12) >= 0x74u )
        {
          v12 = BCryptHashData(phHash, PoolWithTag, 0x54u, 0);
          if ( v12 < 0 )
            goto LABEL_30;
          v12 = BCryptFinishHash(phHash, PoolWithTag + 116, 0x20u, 0);
          if ( v12 < 0 )
            goto LABEL_30;
          if ( RtlCompareMemory(PoolWithTag + 116, PoolWithTag + 84, 0x20u) == 32
            && *((_QWORD *)PoolWithTag + 1) == a4
            && RtlCompareMemory(PoolWithTag + 16, Source2, 0x10u) == 16
            && (v18 = *((_QWORD *)PoolWithTag + 5), v18 <= a4) )
          {
            v15 = *((_QWORD *)PoolWithTag + 5);
            v22 = v15;
            if ( v18 >= a4 )
            {
              if ( a4 + 4095 < a4
                || (v19 = 16 * ((a4 + 4095) >> 12), v20 = v19 + *((unsigned int *)PoolWithTag + 12), v20 < v19) )
              {
                v12 = -1073741675;
                goto LABEL_30;
              }
              v12 = FltQueryInformationFile(
                      *(PFLT_INSTANCE *)(v29 + 120),
                      FileObject,
                      &FileInformation,
                      0x18u,
                      FileStandardInformation,
                      0);
              if ( v12 < 0 )
                goto LABEL_30;
              v15 = v22;
              if ( v20 == *((_QWORD *)&FileInformation + 1) )
              {
                v14 = *((_DWORD *)PoolWithTag + 12);
                v17 = 1;
                v16 = 1;
              }
            }
            else
            {
              v17 = 1;
            }
          }
          else
          {
            v15 = 0;
          }
        }
        *v30 = v16;
        *v31 = v17;
        if ( v32 )
          *v32 = v14;
        if ( a8 )
          *a8 = v15;
      }
    }
  }
LABEL_30:
  if ( phHash )
    BCryptDestroyHash(phHash);
  if ( phAlgorithm )
    BCryptCloseAlgorithmProvider(phAlgorithm, 0);
  if ( PoolWithTag )
    ExFreePoolWithTag(PoolWithTag, 0x69637077u);
  return (unsigned int)v12;
}

```

## disassembly

```asm
0x14002a090  mov     [rsp-8+arg_18], rbx
0x14002a095  push    rbp
0x14002a096  push    rsi
0x14002a097  push    rdi
0x14002a098  push    r12
0x14002a09a  push    r13
0x14002a09c  push    r14
0x14002a09e  push    r15
0x14002a0a0  lea     rbp, [rsp-7]
0x14002a0a5  sub     rsp, 0D0h
0x14002a0ac  mov     rax, cs:__security_cookie
0x14002a0b3  xor     rax, rsp
0x14002a0b6  mov     [rbp+37h+var_38], rax
0x14002a0ba  mov     rax, [rbp+37h+arg_20]
0x14002a0be  mov     rsi, r9
0x14002a0c1  mov     r13, [rbp+37h+arg_38]
0x14002a0c5  mov     r15, rdx
0x14002a0c8  mov     [rbp+37h+var_60], rax
0x14002a0cc  mov     r14, rcx
0x14002a0cf  mov     rax, [rbp+37h+arg_28]
0x14002a0d3  xorps   xmm0, xmm0
0x14002a0d6  mov     [rbp+37h+var_68], rax
0x14002a0da  xor     r9d, r9d; dwFlags
0x14002a0dd  mov     rax, [rbp+37h+arg_30]
0x14002a0e1  xor     edi, edi
0x14002a0e3  mov     [rbp+37h+var_58], rax
0x14002a0e7  xor     eax, eax
0x14002a0e9  mov     [rbp+37h+Source2], r8
0x14002a0ed  xor     r8d, r8d; pszImplementation
0x14002a0f0  mov     [rbp+37h+FileObject], rdx
0x14002a0f4  lea     rdx, pszAlgId; "SHA256"
0x14002a0fb  mov     [rbp+37h+var_70], rcx
0x14002a0ff  lea     rcx, [rbp+37h+phAlgorithm]; phAlgorithm
0x14002a103  mov     [rbp+37h+var_40], rax
0x14002a107  mov     [rbp+37h+phAlgorithm], rax
0x14002a10b  mov     [rbp+37h+phHash], rax
0x14002a10f  mov     qword ptr [rbp+37h+ByteOffset], rax
0x14002a113  mov     [rbp+37h+BytesRead], 0
0x14002a11a  movups  [rbp+37h+FileInformation], xmm0
0x14002a11e  call    cs:__imp_BCryptOpenAlgorithmProvider
0x14002a125  nop     dword ptr [rax+rax+00h]
0x14002a12a  mov     ebx, eax
0x14002a12c  test    eax, eax
0x14002a12e  js      loc_14002A36C
0x14002a134  mov     rcx, [rbp+37h+phAlgorithm]; hAlgorithm
0x14002a138  lea     rdx, [rbp+37h+phHash]; phHash
0x14002a13c  mov     [rsp+100h+dwFlags], edi; dwFlags
0x14002a140  xor     r9d, r9d; cbHashObject
0x14002a143  mov     [rsp+100h+cbSecret], edi; cbSecret
0x14002a147  xor     r8d, r8d; pbHashObject
0x14002a14a  mov     [rsp+100h+pbSecret], rdi; pbSecret
0x14002a14f  call    cs:__imp_BCryptCreateHash
0x14002a156  nop     dword ptr [rax+rax+00h]
0x14002a15b  mov     ebx, eax
0x14002a15d  test    eax, eax
0x14002a15f  js      loc_14002A36C
0x14002a165  mov     edx, 94h; NumberOfBytes
0x14002a16a  lea     ecx, [rdi+1]; PoolType
0x14002a16d  mov     r8d, 69637077h; Tag
0x14002a173  call    cs:__imp_ExAllocatePoolWithTag
0x14002a17a  nop     dword ptr [rax+rax+00h]
0x14002a17f  mov     rdi, rax
0x14002a182  test    rax, rax
0x14002a185  jnz     short loc_14002A191
0x14002a187  mov     ebx, 0C0000017h
0x14002a18c  jmp     loc_14002A36C
0x14002a191  mov     rcx, [r14+78h]; InitiatingInstance
0x14002a195  lea     rax, [rbp+37h+BytesRead]
0x14002a199  mov     [rsp+100h+CallbackContext], 0; CallbackContext
0x14002a1a2  lea     r8, [rbp+37h+ByteOffset]; ByteOffset
0x14002a1a6  mov     [rsp+100h+CallbackRoutine], 0; CallbackRoutine
0x14002a1af  mov     r9d, 74h ; 't'; Length
0x14002a1b5  mov     qword ptr [rsp+100h+dwFlags], rax; BytesRead
0x14002a1ba  mov     rdx, r15; FileObject
0x14002a1bd  mov     [rsp+100h+cbSecret], 0; Flags
0x14002a1c5  mov     [rsp+100h+pbSecret], rdi; Buffer
0x14002a1ca  mov     qword ptr [rbp+37h+ByteOffset], 0
0x14002a1d2  call    cs:__imp_FltReadFile
0x14002a1d9  nop     dword ptr [rax+rax+00h]
0x14002a1de  mov     ebx, eax
0x14002a1e0  test    eax, eax
0x14002a1e2  js      loc_14002A36C
0x14002a1e8  cmp     [rbp+37h+BytesRead], 74h ; 't'
0x14002a1ec  jz      short loc_14002A1F8
0x14002a1ee  mov     ebx, 0C00002C4h
0x14002a1f3  jmp     loc_14002A36C
0x14002a1f8  xor     r12d, r12d
0x14002a1fb  xor     ecx, ecx
0x14002a1fd  xor     r14b, r14b
0x14002a200  xor     r15b, r15b
0x14002a203  cmp     dword ptr [rdi], 69436F57h
0x14002a209  jnz     loc_14002A349
0x14002a20f  cmp     dword ptr [rdi+4], 1
0x14002a213  jnz     loc_14002A349
0x14002a219  cmp     dword ptr [rdi+30h], 74h ; 't'
0x14002a21d  jb      loc_14002A349
0x14002a223  mov     rcx, [rbp+37h+phHash]; hHash
0x14002a227  lea     r8d, [r12+54h]; cbInput
0x14002a22c  xor     r9d, r9d; dwFlags
0x14002a22f  mov     rdx, rdi; pbInput
0x14002a232  call    cs:__imp_BCryptHashData
0x14002a239  nop     dword ptr [rax+rax+00h]
0x14002a23e  mov     ebx, eax
0x14002a240  test    eax, eax
0x14002a242  js      loc_14002A36C
0x14002a248  mov     rcx, [rbp+37h+phHash]; hHash
0x14002a24c  lea     r8d, [r12+20h]; cbOutput
0x14002a251  xor     r9d, r9d; dwFlags
0x14002a254  lea     rdx, [rdi+74h]; pbOutput
0x14002a258  call    cs:__imp_BCryptFinishHash
0x14002a25f  nop     dword ptr [rax+rax+00h]
0x14002a264  mov     ebx, eax
0x14002a266  test    eax, eax
0x14002a268  js      loc_14002A36C
0x14002a26e  lea     rdx, [rdi+54h]; Source2
0x14002a272  lea     r8d, [r12+20h]; Length
0x14002a277  lea     rcx, [rdi+74h]; Source1
0x14002a27b  call    cs:__imp_RtlCompareMemory
0x14002a282  nop     dword ptr [rax+rax+00h]
0x14002a287  cmp     rax, 20h ; ' '
0x14002a28b  jnz     loc_14002A346
0x14002a291  cmp     [rdi+8], rsi
0x14002a295  jnz     loc_14002A346
0x14002a29b  mov     rdx, [rbp+37h+Source2]; Source2
0x14002a29f  lea     rcx, [rdi+10h]; Source1
0x14002a2a3  lea     r8d, [r12+10h]; Length
0x14002a2a8  call    cs:__imp_RtlCompareMemory
0x14002a2af  nop     dword ptr [rax+rax+00h]
0x14002a2b4  cmp     rax, 10h
0x14002a2b8  jnz     loc_14002A346
0x14002a2be  mov     rax, [rdi+28h]
0x14002a2c2  cmp     rax, rsi
0x14002a2c5  ja      short loc_14002A346
0x14002a2c7  mov     rcx, rax
0x14002a2ca  mov     [rbp+37h+var_B0], rax
0x14002a2ce  jnb     short loc_14002A2D5
0x14002a2d0  mov     r15b, 1
0x14002a2d3  jmp     short loc_14002A349
0x14002a2d5  lea     rcx, [rsi+0FFFh]
0x14002a2dc  cmp     rcx, rsi
0x14002a2df  jb      short loc_14002A33F
0x14002a2e1  mov     esi, [rdi+30h]
0x14002a2e4  shr     rcx, 0Ch
0x14002a2e8  shl     rcx, 4
0x14002a2ec  add     rsi, rcx
0x14002a2ef  cmp     rsi, rcx
0x14002a2f2  jb      short loc_14002A33F
0x14002a2f4  mov     rcx, [rbp+37h+var_70]
0x14002a2f8  lea     r8, [rbp+37h+FileInformation]; FileInformation
0x14002a2fc  mov     rdx, [rbp+37h+FileObject]; FileObject
0x14002a300  mov     r9d, 18h; Length
0x14002a306  mov     qword ptr [rsp+100h+cbSecret], r12; LengthReturned
0x14002a30b  mov     dword ptr [rsp+100h+pbSecret], 5; FileInformationClass
0x14002a313  mov     rcx, [rcx+78h]; Instance
0x14002a317  call    cs:__imp_FltQueryInformationFile
0x14002a31e  nop     dword ptr [rax+rax+00h]
0x14002a323  mov     ebx, eax
0x14002a325  test    eax, eax
0x14002a327  js      short loc_14002A36C
0x14002a329  mov     rcx, [rbp+37h+var_B0]
0x14002a32d  cmp     rsi, qword ptr [rbp+37h+FileInformation+8]
0x14002a331  jnz     short loc_14002A349
0x14002a333  mov     r12d, [rdi+30h]
0x14002a337  mov     r15b, 1
0x14002a33a  mov     r14b, r15b
0x14002a33d  jmp     short loc_14002A349
0x14002a33f  mov     ebx, 0C0000095h
0x14002a344  jmp     short loc_14002A36C
0x14002a346  mov     rcx, r12
0x14002a349  mov     rax, [rbp+37h+var_68]
0x14002a34d  mov     [rax], r14b
0x14002a350  mov     rax, [rbp+37h+var_60]
0x14002a354  mov     [rax], r15b
0x14002a357  mov     rax, [rbp+37h+var_58]
0x14002a35b  test    rax, rax
0x14002a35e  jz      short loc_14002A363
0x14002a360  mov     [rax], r12d
0x14002a363  test    r13, r13
0x14002a366  jz      short loc_14002A36C
0x14002a368  mov     [r13+0], rcx
0x14002a36c  mov     rcx, [rbp+37h+phHash]; hHash
0x14002a370  test    rcx, rcx
0x14002a373  jz      short loc_14002A381
0x14002a375  call    cs:__imp_BCryptDestroyHash
0x14002a37c  nop     dword ptr [rax+rax+00h]
0x14002a381  mov     rcx, [rbp+37h+phAlgorithm]; hAlgorithm
0x14002a385  test    rcx, rcx
0x14002a388  jz      short loc_14002A398
0x14002a38a  xor     edx, edx; dwFlags
0x14002a38c  call    cs:__imp_BCryptCloseAlgorithmProvider
0x14002a393  nop     dword ptr [rax+rax+00h]
0x14002a398  test    rdi, rdi
0x14002a39b  jz      short loc_14002A3B1
0x14002a39d  mov     edx, 69637077h; Tag
0x14002a3a2  mov     rcx, rdi; P
0x14002a3a5  call    cs:__imp_ExFreePoolWithTag
0x14002a3ac  nop     dword ptr [rax+rax+00h]
0x14002a3b1  mov     eax, ebx
0x14002a3b3  mov     rcx, [rbp+37h+var_38]
0x14002a3b7  xor     rcx, rsp; StackCookie
0x14002a3ba  call    __security_check_cookie
0x14002a3bf  mov     rbx, [rsp+100h+arg_18]
0x14002a3c7  add     rsp, 0D0h
0x14002a3ce  pop     r15
0x14002a3d0  pop     r14
0x14002a3d2  pop     r13
0x14002a3d4  pop     r12
0x14002a3d6  pop     rdi
0x14002a3d7  pop     rsi
0x14002a3d8  pop     rbp
0x14002a3d9  retn
```
