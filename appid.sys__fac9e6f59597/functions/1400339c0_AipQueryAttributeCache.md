# AipQueryAttributeCache

- ea: `0x1400339c0`
- end: `0x140033d45`
- name: `AipQueryAttributeCache`
- size: `901`
- prototype: `void __fastcall(__int64, __int64)`
- caller_count: `2`
- callee_count: `10`
- tags: `broker_com_uri`

## callers

- `0x1400333b0`
- `0x1400360a0`

## callees

- `0x14000161d`
- `0x140003320`
- `0x1400033b4`
- `0x140003570`
- `0x140025964`
- `0x140027bf0`
- `0x14002a9ac`
- `0x140032a50`
- `0x1400339c0`
- `0x140036ee0`

## import_xrefs

- `ntoskrnl!FsRtlQueryKernelEaFile` at `0x140033b51`
- `ntoskrnl!FsRtlQueryKernelEaFile` at `0x140033b51`
- `ntoskrnl!ExFreePoolWithTag` at `0x140033d01`
- `ntoskrnl!ExFreePoolWithTag` at `0x140033d1c`
- `ntoskrnl!ExFreePoolWithTag` at `0x140033d01`
- `ntoskrnl!ExFreePoolWithTag` at `0x140033d1c`

## pseudocode

```c
void __fastcall AipQueryAttributeCache(__int64 a1, __int64 a2)
{
  unsigned int i; // edx
  unsigned int v5; // edi
  unsigned int v6; // ebp
  char v7; // r14
  char *v8; // r12
  void *v9; // r15
  bool IsFileEaCacheable; // al
  __int64 v11; // rax
  __int64 v12; // r8
  const char *v13; // rdi
  __int64 v14; // rax
  unsigned int j; // eax
  int v16; // ebx
  char v17; // [rsp+38h] [rbp-50h]
  unsigned int v18; // [rsp+98h] [rbp+10h] BYREF
  __int64 v19; // [rsp+A0h] [rbp+18h] BYREF
  _DWORD *v20; // [rsp+A8h] [rbp+20h] BYREF

  v18 = 0;
  for ( i = 0; i < 3; ++i )
  {
    if ( *(_DWORD *)(a2 + 4LL * i + 12) )
    {
      v5 = 352;
      v6 = 37;
      v7 = 1;
      goto LABEL_7;
    }
  }
  v7 = 0;
  *(_DWORD *)(a1 + 200) = 0;
  v5 = 0;
  v6 = 0;
LABEL_7:
  if ( *(_DWORD *)(a2 + 4) )
  {
    v5 += 4096;
    v6 = ((v6 + 3) & 0xFFFFFFFC) + 39;
  }
  else if ( !*(_DWORD *)(a2 + 8) )
  {
    goto LABEL_11;
  }
  v5 += 0x2000;
  v6 = ((v6 + 3) & 0xFFFFFFFC) + 40;
LABEL_11:
  if ( !v5 )
    return;
  v8 = 0;
  v9 = 0;
  IsFileEaCacheable = AiIsFileEaCacheable(*(void **)(a1 + 8));
  *(_DWORD *)(a1 + 112) = IsFileEaCacheable;
  if ( IsFileEaCacheable )
  {
    v8 = (char *)AiAlloc(v5);
    v11 = AiAlloc(v6);
    v9 = (void *)v11;
    if ( !v8 || !v11 )
    {
      *(_DWORD *)(a1 + 200) = -1073741801;
      goto LABEL_45;
    }
    v19 = v11;
    v12 = v11;
    v20 = 0;
    if ( v7 )
    {
      AiAddEaToQueryBuffer("$KERNEL.PURGE.APPID.HASHINFO", &v20, v11, &v19);
      v12 = v19;
    }
    if ( *(_DWORD *)(a2 + 4)
      && (AiAddEaToQueryBuffer("$KERNEL.PURGE.APPID.SIGNERINFO", &v20, v12, &v19), v12 = v19, *(_DWORD *)(a2 + 4))
      || *(_DWORD *)(a2 + 8) )
    {
      AiAddEaToQueryBuffer("$KERNEL.PURGE.APPID.VERSIONINFO", &v20, v12, &v19);
    }
    v17 = 0;
    if ( (int)FsRtlQueryKernelEaFile(*(_QWORD *)(a1 + 16), v8, v5, 0, v9, v6, 0, v17, &v18) < 0 )
    {
      *(_DWORD *)(a1 + 112) = 0;
      goto LABEL_40;
    }
    v13 = v8;
    do
    {
      v18 = *((unsigned __int8 *)v13 + 5) + 9 + *((unsigned __int16 *)v13 + 3);
      if ( !stricmp_0(v13 + 8, "$KERNEL.PURGE.APPID.HASHINFO") )
      {
        *(_DWORD *)(a1 + 200) = AiGetHashInfoFromCache((__int64)v13, v18, a1 + 204, a1 + 300);
      }
      else if ( !stricmp_0(v13 + 8, "$KERNEL.PURGE.APPID.SIGNERINFO") )
      {
        *(_DWORD *)(a1 + 420) = AiGetTrustedPublisherNameFromCache(
                                  (__int64)v13,
                                  v18,
                                  (_BYTE *)(a1 + 416),
                                  (struct _UNICODE_STRING *)(a1 + 424));
      }
      else if ( !stricmp_0(v13 + 8, "$KERNEL.PURGE.APPID.VERSIONINFO") )
      {
        *(_DWORD *)(a1 + 360) = AiGetVersionInfoFromCache(
                                  (__int64)v13,
                                  v18,
                                  (_DWORD *)(a1 + 364),
                                  (_DWORD *)(a1 + 368),
                                  (_DWORD *)(a1 + 372),
                                  (_DWORD *)(a1 + 376),
                                  a1 + 384,
                                  a1 + 400);
      }
      v14 = *(unsigned int *)v13;
      if ( !(_DWORD)v14 )
        break;
      v13 += v14;
    }
    while ( v13 );
  }
  if ( *(int *)(a1 + 200) < 0 )
    goto LABEL_41;
  for ( j = 0; j < 3; ++j )
  {
    if ( !*(_DWORD *)(a1 + 4LL * j + 300) && *(_DWORD *)(a2 + 4LL * j + 12) )
    {
      *(_DWORD *)(a1 + 200) = -2;
      break;
    }
  }
LABEL_40:
  if ( *(int *)(a1 + 200) < 0 )
  {
LABEL_41:
    v16 = AppHashComputeFileHashes(*(_QWORD *)(a1 + 8), a2 + 12, a1 + 204, a1 + 300);
    if ( v16 >= 0 && *(_DWORD *)(a1 + 112) )
      AiSetHashInfoInCache(*(_QWORD *)(a1 + 16), a1 + 300, a1 + 204);
    *(_DWORD *)(a1 + 200) = v16;
  }
LABEL_45:
  if ( v8 )
    ExFreePoolWithTag(v8, 0);
  if ( v9 )
    ExFreePoolWithTag(v9, 0);
}

```

## disassembly

```asm
0x1400339c0  mov     rax, rsp
0x1400339c3  push    rbx
0x1400339c4  push    rsi
0x1400339c5  push    rdi
0x1400339c6  push    r13
0x1400339c8  sub     rsp, 68h
0x1400339cc  xor     r13d, r13d
0x1400339cf  mov     [rax+8], rbp
0x1400339d3  mov     rbx, rdx
0x1400339d6  mov     [rax+10h], r13d
0x1400339da  mov     edx, r13d
0x1400339dd  mov     [rax-30h], r14
0x1400339e1  mov     rsi, rcx
0x1400339e4  cmp     edx, 3
0x1400339e7  jnb     short loc_140033A05
0x1400339e9  mov     eax, edx
0x1400339eb  cmp     [rbx+rax*4+0Ch], r13d
0x1400339f0  jnz     short loc_1400339F6
0x1400339f2  inc     edx
0x1400339f4  jmp     short loc_1400339E4
0x1400339f6  mov     edi, 160h
0x1400339fb  mov     ebp, 25h ; '%'
0x140033a00  mov     r14b, 1
0x140033a03  jmp     short loc_140033A15
0x140033a05  xor     r14b, r14b
0x140033a08  mov     [rcx+0C8h], r13d
0x140033a0f  mov     edi, r13d
0x140033a12  mov     ebp, r13d
0x140033a15  cmp     [rbx+4], r13d
0x140033a19  jz      short loc_140033A2C
0x140033a1b  add     ebp, 3
0x140033a1e  add     edi, 1000h
0x140033a24  and     ebp, 0FFFFFFFCh
0x140033a27  add     ebp, 27h ; '''
0x140033a2a  jmp     short loc_140033A32
0x140033a2c  cmp     [rbx+8], r13d
0x140033a30  jz      short loc_140033A41
0x140033a32  add     ebp, 3
0x140033a35  add     edi, 2000h
0x140033a3b  and     ebp, 0FFFFFFFCh
0x140033a3e  add     ebp, 28h ; '('
0x140033a41  test    edi, edi
0x140033a43  jz      loc_140033D2D
0x140033a49  mov     rcx, [rcx+8]
0x140033a4d  mov     [rsp+88h+var_28], r12
0x140033a52  mov     r12, r13
0x140033a55  mov     [rsp+88h+var_38], r15
0x140033a5a  mov     r15, r13
0x140033a5d  call    AiIsFileEaCacheable
0x140033a62  movzx   eax, al
0x140033a65  mov     [rsi+70h], eax
0x140033a68  test    eax, eax
0x140033a6a  jz      loc_140033C6C
0x140033a70  mov     ecx, edi
0x140033a72  call    AiAlloc
0x140033a77  mov     ecx, ebp
0x140033a79  mov     r12, rax
0x140033a7c  call    AiAlloc
0x140033a81  mov     r15, rax
0x140033a84  test    r12, r12
0x140033a87  jz      loc_140033C94
0x140033a8d  test    rax, rax
0x140033a90  jz      loc_140033C94
0x140033a96  mov     [rsp+88h+arg_10], rax
0x140033a9e  mov     r8, rax
0x140033aa1  mov     [rsp+88h+arg_18], r13
0x140033aa9  test    r14b, r14b
0x140033aac  jz      short loc_140033AD2
0x140033aae  lea     r9, [rsp+88h+arg_10]
0x140033ab6  lea     rdx, [rsp+88h+arg_18]
0x140033abe  lea     rcx, aKernelPurgeApp; "$KERNEL.PURGE.APPID.HASHINFO"
0x140033ac5  call    AiAddEaToQueryBuffer
0x140033aca  mov     r8, [rsp+88h+arg_10]
0x140033ad2  cmp     [rbx+4], r13d
0x140033ad6  jz      short loc_140033B02
0x140033ad8  lea     r9, [rsp+88h+arg_10]
0x140033ae0  lea     rdx, [rsp+88h+arg_18]
0x140033ae8  lea     rcx, aKernelPurgeApp_1; "$KERNEL.PURGE.APPID.SIGNERINFO"
0x140033aef  call    AiAddEaToQueryBuffer
0x140033af4  mov     r8, [rsp+88h+arg_10]
0x140033afc  cmp     [rbx+4], r13d
0x140033b00  jnz     short loc_140033B08
0x140033b02  cmp     [rbx+8], r13d
0x140033b06  jz      short loc_140033B24
0x140033b08  lea     r9, [rsp+88h+arg_10]
0x140033b10  lea     rdx, [rsp+88h+arg_18]
0x140033b18  lea     rcx, aKernelPurgeApp_0; "$KERNEL.PURGE.APPID.VERSIONINFO"
0x140033b1f  call    AiAddEaToQueryBuffer
0x140033b24  mov     rcx, [rsi+10h]
0x140033b28  lea     rax, [rsp+88h+arg_8]
0x140033b30  mov     [rsp+88h+var_48], rax
0x140033b35  xor     r9d, r9d
0x140033b38  mov     byte ptr [rsp+88h+var_50], r13b
0x140033b3d  mov     r8d, edi
0x140033b40  mov     [rsp+88h+var_58], r13
0x140033b45  mov     rdx, r12
0x140033b48  mov     dword ptr [rsp+88h+var_60], ebp
0x140033b4c  mov     [rsp+88h+var_68], r15
0x140033b51  call    cs:__imp_FsRtlQueryKernelEaFile
0x140033b58  nop     dword ptr [rax+rax+00h]
0x140033b5d  test    eax, eax
0x140033b5f  jns     short loc_140033B6A
0x140033b61  mov     [rsi+70h], r13d
0x140033b65  jmp     loc_140033CAA
0x140033b6a  mov     rdi, r12
0x140033b6d  movzx   ecx, word ptr [rdi+6]
0x140033b71  lea     rdx, aKernelPurgeApp; "$KERNEL.PURGE.APPID.HASHINFO"
0x140033b78  movzx   eax, byte ptr [rdi+5]
0x140033b7c  add     eax, 9
0x140033b7f  add     ecx, eax
0x140033b81  mov     [rsp+88h+arg_8], ecx
0x140033b88  lea     rcx, [rdi+8]; Str1
0x140033b8c  call    _stricmp_0
0x140033b91  test    eax, eax
0x140033b93  jnz     short loc_140033BBD
0x140033b95  mov     edx, [rsp+88h+arg_8]
0x140033b9c  lea     r9, [rsi+12Ch]
0x140033ba3  lea     r8, [rsi+0CCh]
0x140033baa  mov     rcx, rdi
0x140033bad  call    AiGetHashInfoFromCache
0x140033bb2  mov     [rsi+0C8h], eax
0x140033bb8  jmp     loc_140033C5D
0x140033bbd  lea     rdx, aKernelPurgeApp_1; "$KERNEL.PURGE.APPID.SIGNERINFO"
0x140033bc4  lea     rcx, [rdi+8]; Str1
0x140033bc8  call    _stricmp_0
0x140033bcd  test    eax, eax
0x140033bcf  jnz     short loc_140033BF6
0x140033bd1  mov     edx, [rsp+88h+arg_8]
0x140033bd8  lea     r9, [rsi+1A8h]
0x140033bdf  lea     r8, [rsi+1A0h]
0x140033be6  mov     rcx, rdi
0x140033be9  call    AiGetTrustedPublisherNameFromCache
0x140033bee  mov     [rsi+1A4h], eax
0x140033bf4  jmp     short loc_140033C5D
0x140033bf6  lea     rdx, aKernelPurgeApp_0; "$KERNEL.PURGE.APPID.VERSIONINFO"
0x140033bfd  lea     rcx, [rdi+8]; Str1
0x140033c01  call    _stricmp_0
0x140033c06  test    eax, eax
0x140033c08  jnz     short loc_140033C5D
0x140033c0a  lea     rdx, [rsi+178h]
0x140033c11  lea     rax, [rsi+190h]
0x140033c18  mov     [rsp+88h+var_50], rax
0x140033c1d  lea     rcx, [rsi+180h]
0x140033c24  mov     [rsp+88h+var_58], rcx
0x140033c29  lea     r10, [rsi+174h]
0x140033c30  mov     [rsp+88h+var_60], rdx
0x140033c35  lea     r9, [rsi+170h]
0x140033c3c  mov     edx, [rsp+88h+arg_8]
0x140033c43  lea     r8, [rsi+16Ch]
0x140033c4a  mov     rcx, rdi
0x140033c4d  mov     [rsp+88h+var_68], r10
0x140033c52  call    AiGetVersionInfoFromCache
0x140033c57  mov     [rsi+168h], eax
0x140033c5d  mov     eax, [rdi]
0x140033c5f  test    eax, eax
0x140033c61  jz      short loc_140033C6C
0x140033c63  add     rdi, rax
0x140033c66  jnz     loc_140033B6D
0x140033c6c  cmp     [rsi+0C8h], r13d
0x140033c73  jl      short loc_140033CB3
0x140033c75  mov     eax, r13d
0x140033c78  cmp     eax, 3
0x140033c7b  jnb     short loc_140033CAA
0x140033c7d  mov     ecx, eax
0x140033c7f  cmp     [rsi+rcx*4+12Ch], r13d
0x140033c87  jnz     short loc_140033C90
0x140033c89  cmp     [rbx+rcx*4+0Ch], r13d
0x140033c8e  jnz     short loc_140033CA0
0x140033c90  inc     eax
0x140033c92  jmp     short loc_140033C78
0x140033c94  mov     dword ptr [rsi+0C8h], 0C0000017h
0x140033c9e  jmp     short loc_140033CF7
0x140033ca0  mov     dword ptr [rsi+0C8h], 0FFFFFFFEh
0x140033caa  cmp     [rsi+0C8h], r13d
0x140033cb1  jge     short loc_140033CF7
0x140033cb3  mov     rcx, [rsi+8]
0x140033cb7  lea     rdx, [rbx+0Ch]
0x140033cbb  lea     r9, [rsi+12Ch]
0x140033cc2  lea     r8, [rsi+0CCh]
0x140033cc9  call    AppHashComputeFileHashes
0x140033cce  mov     ebx, eax
0x140033cd0  test    eax, eax
0x140033cd2  js      short loc_140033CF1
0x140033cd4  cmp     [rsi+70h], r13d
0x140033cd8  jz      short loc_140033CF1
0x140033cda  mov     rcx, [rsi+10h]
0x140033cde  lea     r8, [rsi+0CCh]
0x140033ce5  lea     rdx, [rsi+12Ch]
0x140033cec  call    AiSetHashInfoInCache
0x140033cf1  mov     [rsi+0C8h], ebx
0x140033cf7  test    r12, r12
0x140033cfa  jz      short loc_140033D0D
0x140033cfc  xor     edx, edx; Tag
0x140033cfe  mov     rcx, r12; P
0x140033d01  call    cs:__imp_ExFreePoolWithTag
0x140033d08  nop     dword ptr [rax+rax+00h]
0x140033d0d  mov     r12, [rsp+88h+var_28]
0x140033d12  test    r15, r15
0x140033d15  jz      short loc_140033D28
0x140033d17  xor     edx, edx; Tag
0x140033d19  mov     rcx, r15; P
0x140033d1c  call    cs:__imp_ExFreePoolWithTag
0x140033d23  nop     dword ptr [rax+rax+00h]
0x140033d28  mov     r15, [rsp+88h+var_38]
0x140033d2d  mov     r14, [rsp+88h+var_30]
0x140033d32  mov     rbp, [rsp+88h+arg_0]
0x140033d3a  add     rsp, 68h
0x140033d3e  pop     r13
0x140033d40  pop     rdi
0x140033d41  pop     rsi
0x140033d42  pop     rbx
0x140033d43  retn
```
