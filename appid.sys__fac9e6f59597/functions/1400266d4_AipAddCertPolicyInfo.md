# AipAddCertPolicyInfo

- ea: `0x1400266d4`
- end: `0x14002693b`
- name: `AipAddCertPolicyInfo`
- size: `615`
- prototype: `__int64 __fastcall(_QWORD *, const UNICODE_STRING *, char)`
- caller_count: `1`
- callee_count: `10`
- tags: `registry_config`

## callers

- `0x140025560`

## callees

- `0x140001ee0`
- `0x140006b20`
- `0x140006c40`
- `0x140006f40`
- `0x1400266d4`
- `0x140026944`
- `0x140026afc`
- `0x140026c08`
- `0x140032a50`
- `0x1400331a0`

## import_xrefs

- `ntoskrnl!RtlCopyUnicodeString` at `0x1400267cc`
- `ntoskrnl!RtlCopyUnicodeString` at `0x1400267cc`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140026919`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140026919`
- `ntoskrnl!KeEnterCriticalRegion` at `0x14002687f`
- `ntoskrnl!KeEnterCriticalRegion` at `0x14002687f`
- `ntoskrnl!RtlAvlInsertNodeEx` at `0x1400268f8`
- `ntoskrnl!RtlAvlInsertNodeEx` at `0x1400268f8`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x140026894`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x140026894`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x14002690d`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x14002690d`
- `ntoskrnl!ZwClose` at `0x140026840`
- `ntoskrnl!ZwClose` at `0x140026840`

## pseudocode

```c
__int64 __fastcall AipAddCertPolicyInfo(_QWORD *a1, const UNICODE_STRING *a2, char a3)
{
  char *v6; // rax
  char *v7; // rbx
  int v8; // edi
  unsigned int v9; // edx
  __int64 v10; // r9
  __int64 v11; // rcx
  __int64 v12; // r8
  __int64 v13; // rcx
  __int64 v14; // rax
  unsigned int v15; // eax
  void *v16; // rax
  __int64 v17; // rsi
  __int64 v18; // r8
  size_t v19; // rbp
  __int64 v20; // rax
  HANDLE Handle; // [rsp+58h] [rbp+10h] BYREF

  Handle = 0;
  if ( !a2 && !a3 )
    return 3221225485LL;
  v6 = (char *)AiAlloc(0x68u);
  v7 = v6;
  if ( !v6 )
    return 3221225495LL;
  memset(v6, 0, 0x68u);
  v8 = AipAllocCertName(a1, v7);
  if ( v8 >= 0 )
  {
    v9 = 0;
    *((_QWORD *)v7 + 10) = a1[5];
    *((_QWORD *)v7 + 9) = a1[4];
    v10 = a1[2];
    while ( v9 < *(_DWORD *)(v10 + 32) )
    {
      v11 = *(_QWORD *)(v10 + 24);
      if ( *(_DWORD *)(v11 + 16LL * v9) == 12 )
      {
        v12 = *(_QWORD *)(v11 + 16LL * v9 + 8);
        v13 = rgbOID_LIFETIME_SIGNING - *(_QWORD *)v12;
        if ( rgbOID_LIFETIME_SIGNING == *(_QWORD *)v12 )
          v13 = 218303031LL - *(unsigned int *)(v12 + 8);
        if ( !v13 )
        {
          *((_DWORD *)v7 + 24) = 1;
          break;
        }
      }
      ++v9;
    }
    if ( a2 )
    {
      *((_WORD *)v7 + 21) = a2->MaximumLength;
      v14 = AiAlloc(a2->MaximumLength);
      *((_QWORD *)v7 + 6) = v14;
      if ( !v14 )
      {
LABEL_17:
        v8 = -1073741801;
        goto LABEL_36;
      }
      RtlCopyUnicodeString((PUNICODE_STRING)(v7 + 40), a2);
    }
    v15 = **(_DWORD **)(a1[2] + 8LL);
    *((_DWORD *)v7 + 14) = v15;
    v16 = (void *)AiAlloc(v15);
    *((_QWORD *)v7 + 8) = v16;
    if ( v16 )
    {
      memmove(v16, *(const void **)(*(_QWORD *)(a1[2] + 8LL) + 8LL), *((unsigned int *)v7 + 14));
      v8 = AiRegOpenKey(0, &qword_140009510, 131078, &Handle);
      if ( v8 >= 0 )
      {
        v8 = AipAddCertToCertStore(Handle, v7);
        ZwClose(Handle);
      }
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x80u) != 0 )
      {
        WPP_SF_Z(WPP_GLOBAL_Control->AttachedDevice, 14, WPP_f0937eb5e67f36495f963cc4c3825ed9_Traceguids, v7 + 40);
      }
      KeEnterCriticalRegion();
      ExAcquirePushLockExclusiveEx(&qword_1400195D8, 0);
      v17 = AipCertificateStore;
      LOBYTE(v18) = 0;
      if ( AipCertificateStore )
      {
        v19 = *((unsigned int *)v7 + 14);
        while ( 1 )
        {
          if ( (unsigned int)v19 < *(_DWORD *)(v17 + 56)
            || (unsigned int)v19 <= *(_DWORD *)(v17 + 56)
            && memcmp(*((const void **)v7 + 8), *(const void **)(v17 + 64), v19) < 0 )
          {
            v20 = *(_QWORD *)v17;
            if ( !*(_QWORD *)v17 )
            {
              LOBYTE(v18) = 0;
              break;
            }
          }
          else
          {
            v20 = *(_QWORD *)(v17 + 8);
            if ( !v20 )
            {
              LOBYTE(v18) = 1;
              break;
            }
          }
          v17 = v20;
        }
      }
      RtlAvlInsertNodeEx(&AipCertificateStore, v17, v18, v7);
      ExReleasePushLockExclusiveEx(&qword_1400195D8, 0);
      KeLeaveCriticalRegion();
      v7 = 0;
      goto LABEL_36;
    }
    goto LABEL_17;
  }
LABEL_36:
  AipFreeCert(v7);
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x1400266d4  push    rbx
0x1400266d6  push    rbp
0x1400266d7  push    rsi
0x1400266d8  push    rdi
0x1400266d9  sub     rsp, 28h
0x1400266dd  mov     [rsp+48h+Handle], 0
0x1400266e6  mov     rsi, rdx
0x1400266e9  mov     rbp, rcx
0x1400266ec  test    rdx, rdx
0x1400266ef  jnz     short loc_140026700
0x1400266f1  test    r8b, r8b
0x1400266f4  jnz     short loc_140026700
0x1400266f6  mov     eax, 0C000000Dh
0x1400266fb  jmp     loc_140026931
0x140026700  mov     edi, 68h ; 'h'
0x140026705  mov     ecx, edi
0x140026707  call    AiAlloc
0x14002670c  mov     rbx, rax
0x14002670f  test    rax, rax
0x140026712  jnz     short loc_14002671E
0x140026714  mov     eax, 0C0000017h
0x140026719  jmp     loc_140026931
0x14002671e  mov     r8, rdi; Size
0x140026721  xor     edx, edx; Val
0x140026723  mov     rcx, rbx; void *
0x140026726  call    memset
0x14002672b  mov     rdx, rbx
0x14002672e  mov     rcx, rbp
0x140026731  call    AipAllocCertName
0x140026736  mov     edi, eax
0x140026738  test    eax, eax
0x14002673a  js      loc_140026927
0x140026740  mov     rax, [rbp+28h]
0x140026744  xor     edx, edx
0x140026746  mov     [rbx+50h], rax
0x14002674a  mov     rax, [rbp+20h]
0x14002674e  mov     [rbx+48h], rax
0x140026752  mov     r9, [rbp+10h]
0x140026756  mov     r10d, [r9+20h]
0x14002675a  cmp     edx, r10d
0x14002675d  jnb     short loc_14002679C
0x14002675f  mov     rcx, [r9+18h]
0x140026763  mov     eax, edx
0x140026765  add     rax, rax
0x140026768  cmp     dword ptr [rcx+rax*8], 0Ch
0x14002676c  jnz     short loc_140026791
0x14002676e  mov     r8, [rcx+rax*8+8]
0x140026773  mov     rcx, cs:rgbOID_LIFETIME_SIGNING
0x14002677a  sub     rcx, [r8]
0x14002677d  jnz     short loc_14002678C
0x14002677f  mov     ecx, cs:dword_14000C658
0x140026785  mov     eax, [r8+8]
0x140026789  sub     rcx, rax
0x14002678c  test    rcx, rcx
0x14002678f  jz      short loc_140026795
0x140026791  inc     edx
0x140026793  jmp     short loc_14002675A
0x140026795  mov     dword ptr [rbx+60h], 1
0x14002679c  test    rsi, rsi
0x14002679f  jz      short loc_1400267D8
0x1400267a1  movzx   eax, word ptr [rsi+2]
0x1400267a5  mov     [rbx+2Ah], ax
0x1400267a9  movzx   ecx, word ptr [rsi+2]
0x1400267ad  call    AiAlloc
0x1400267b2  mov     [rbx+30h], rax
0x1400267b6  test    rax, rax
0x1400267b9  jnz     short loc_1400267C5
0x1400267bb  mov     edi, 0C0000017h
0x1400267c0  jmp     loc_140026927
0x1400267c5  lea     rcx, [rbx+28h]; DestinationString
0x1400267c9  mov     rdx, rsi; SourceString
0x1400267cc  call    cs:__imp_RtlCopyUnicodeString
0x1400267d3  nop     dword ptr [rax+rax+00h]
0x1400267d8  mov     rax, [rbp+10h]
0x1400267dc  mov     rcx, [rax+8]
0x1400267e0  mov     eax, [rcx]
0x1400267e2  mov     ecx, eax
0x1400267e4  mov     [rbx+38h], eax
0x1400267e7  call    AiAlloc
0x1400267ec  mov     [rbx+40h], rax
0x1400267f0  mov     rcx, rax; void *
0x1400267f3  test    rax, rax
0x1400267f6  jz      short loc_1400267BB
0x1400267f8  mov     rax, [rbp+10h]
0x1400267fc  mov     r8d, [rbx+38h]; Size
0x140026800  mov     rdx, [rax+8]
0x140026804  mov     rdx, [rdx+8]; Src
0x140026808  call    memmove
0x14002680d  lea     r9, [rsp+48h+Handle]
0x140026812  mov     r8d, 20006h
0x140026818  lea     rdx, qword_140009510
0x14002681f  xor     ecx, ecx
0x140026821  call    AiRegOpenKey
0x140026826  mov     edi, eax
0x140026828  test    eax, eax
0x14002682a  js      short loc_14002684C
0x14002682c  mov     rcx, [rsp+48h+Handle]
0x140026831  mov     rdx, rbx
0x140026834  call    AipAddCertToCertStore
0x140026839  mov     rcx, [rsp+48h+Handle]; Handle
0x14002683e  mov     edi, eax
0x140026840  call    cs:__imp_ZwClose
0x140026847  nop     dword ptr [rax+rax+00h]
0x14002684c  mov     rcx, cs:WPP_GLOBAL_Control
0x140026853  lea     rax, WPP_GLOBAL_Control
0x14002685a  cmp     rcx, rax
0x14002685d  jz      short loc_14002687F
0x14002685f  mov     eax, [rcx+2Ch]
0x140026862  test    al, al
0x140026864  jns     short loc_14002687F
0x140026866  mov     rcx, [rcx+18h]
0x14002686a  lea     r9, [rbx+28h]
0x14002686e  mov     edx, 0Eh
0x140026873  lea     r8, WPP_f0937eb5e67f36495f963cc4c3825ed9_Traceguids
0x14002687a  call    WPP_SF_Z
0x14002687f  call    cs:__imp_KeEnterCriticalRegion
0x140026886  nop     dword ptr [rax+rax+00h]
0x14002688b  xor     edx, edx
0x14002688d  lea     rcx, qword_1400195D8
0x140026894  call    cs:__imp_ExAcquirePushLockExclusiveEx
0x14002689b  nop     dword ptr [rax+rax+00h]
0x1400268a0  mov     rsi, cs:AipCertificateStore
0x1400268a7  xor     r8b, r8b
0x1400268aa  test    rsi, rsi
0x1400268ad  jz      short loc_1400268EB
0x1400268af  mov     ebp, [rbx+38h]
0x1400268b2  cmp     ebp, [rsi+38h]
0x1400268b5  jb      short loc_1400268DB
0x1400268b7  ja      short loc_1400268CD
0x1400268b9  mov     rdx, [rsi+40h]; Buf2
0x1400268bd  mov     r8, rbp; Size
0x1400268c0  mov     rcx, [rbx+40h]; Buf1
0x1400268c4  call    memcmp
0x1400268c9  test    eax, eax
0x1400268cb  js      short loc_1400268DB
0x1400268cd  mov     rax, [rsi+8]
0x1400268d1  test    rax, rax
0x1400268d4  jnz     short loc_1400268E3
0x1400268d6  mov     r8b, 1
0x1400268d9  jmp     short loc_1400268EB
0x1400268db  mov     rax, [rsi]
0x1400268de  test    rax, rax
0x1400268e1  jz      short loc_1400268E8
0x1400268e3  mov     rsi, rax
0x1400268e6  jmp     short loc_1400268B2
0x1400268e8  xor     r8b, r8b
0x1400268eb  mov     r9, rbx
0x1400268ee  lea     rcx, AipCertificateStore
0x1400268f5  mov     rdx, rsi
0x1400268f8  call    cs:__imp_RtlAvlInsertNodeEx
0x1400268ff  nop     dword ptr [rax+rax+00h]
0x140026904  xor     edx, edx
0x140026906  lea     rcx, qword_1400195D8
0x14002690d  call    cs:__imp_ExReleasePushLockExclusiveEx
0x140026914  nop     dword ptr [rax+rax+00h]
0x140026919  call    cs:__imp_KeLeaveCriticalRegion
0x140026920  nop     dword ptr [rax+rax+00h]
0x140026925  xor     ebx, ebx
0x140026927  mov     rcx, rbx
0x14002692a  call    AipFreeCert
0x14002692f  mov     eax, edi
0x140026931  add     rsp, 28h
0x140026935  pop     rdi
0x140026936  pop     rsi
0x140026937  pop     rbp
0x140026938  pop     rbx
0x140026939  retn
```
