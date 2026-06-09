# ConvertTrusteeWToTrusteeA(_TRUSTEE_W *,_TRUSTEE_A * *)

- ea: `0x18004ccf0`
- end: `0x18004ce34`
- name: `?ConvertTrusteeWToTrusteeA@@YAKPEAU_TRUSTEE_W@@PEAPEAU_TRUSTEE_A@@@Z`
- size: `324`
- prototype: `unsigned int __fastcall(struct _TRUSTEE_W *, struct _TRUSTEE_A **)`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, loader_planting`

## callers

- `0x1800491f0`

## callees

- `0x18004ccf0`

## import_xrefs

- `ntdll!RtlLengthSid` at `0x18004cd92`
- `ntdll!RtlLengthSid` at `0x18004cd92`
- `ntdll!RtlValidSid` at `0x18004cd7a`
- `ntdll!RtlValidSid` at `0x18004cd7a`
- `ntdll!RtlCopySid` at `0x18004ce12`
- `ntdll!RtlCopySid` at `0x18004ce12`
- `ntdll!RtlUnicodeToMultiByteN` at `0x18004cdf5`
- `ntdll!RtlUnicodeToMultiByteN` at `0x18004cdf5`
- `ntdll!RtlNtStatusToDosErrorNoTeb` at `0x18004cd51`
- `ntdll!RtlNtStatusToDosErrorNoTeb` at `0x18004ce01`
- `ntdll!RtlNtStatusToDosErrorNoTeb` at `0x18004cd51`
- `ntdll!RtlNtStatusToDosErrorNoTeb` at `0x18004ce01`
- `ntdll!RtlUnicodeToMultiByteSize` at `0x18004cd45`
- `ntdll!RtlUnicodeToMultiByteSize` at `0x18004cd45`
- `KERNELBASE!LocalAlloc` at `0x18004cda7`
- `KERNELBASE!LocalAlloc` at `0x18004cda7`

## pseudocode

```c
__int64 __fastcall ConvertTrusteeWToTrusteeA(struct _TRUSTEE_W *a1, struct _TRUSTEE_A **a2)
{
  ULONG v4; // ebx
  __int64 v5; // rsi
  WCHAR *ptstrName; // rdx
  __int64 v7; // r8
  int v8; // eax
  ULONG v9; // eax
  char *v10; // rax
  LPWCH v11; // r8
  int v12; // eax
  ULONG BytesInMultiByteString; // [rsp+50h] [rbp+8h] BYREF

  v4 = 0;
  if ( !a1 )
  {
    *a2 = 0;
    return v4;
  }
  v5 = -1;
  BytesInMultiByteString = 0;
  if ( a1->TrusteeForm != TRUSTEE_IS_NAME )
  {
    if ( a1->TrusteeForm )
      return 87;
    if ( !RtlValidSid(a1->ptstrName) )
      return 1337;
    v9 = RtlLengthSid(a1->ptstrName);
    BytesInMultiByteString = v9;
    goto LABEL_14;
  }
  ptstrName = a1->ptstrName;
  v7 = -1;
  do
    ++v7;
  while ( ptstrName[v7] );
  v8 = RtlUnicodeToMultiByteSize(&BytesInMultiByteString, ptstrName, 2 * v7 + 2);
  if ( v8 < 0 )
    v4 = RtlNtStatusToDosErrorNoTeb(v8);
  v9 = ++BytesInMultiByteString;
  if ( !v4 )
  {
LABEL_14:
    v10 = (char *)LocalAlloc(0x40u, v9 + 32LL);
    *a2 = (struct _TRUSTEE_A *)v10;
    if ( v10 )
    {
      *(_OWORD *)v10 = *(_OWORD *)&a1->pMultipleTrustee;
      *((_OWORD *)v10 + 1) = *(_OWORD *)&a1->TrusteeType;
      *((_QWORD *)v10 + 3) = v10 + 32;
      v11 = a1->ptstrName;
      if ( a1->TrusteeForm == TRUSTEE_IS_NAME )
      {
        do
          ++v5;
        while ( v11[v5] );
        v12 = RtlUnicodeToMultiByteN(v10 + 32, 2 * v5 + 2, 0, a1->ptstrName, 2 * v5 + 2);
        if ( v12 < 0 )
          return RtlNtStatusToDosErrorNoTeb(v12);
      }
      else
      {
        RtlCopySid(BytesInMultiByteString, v10 + 32, v11);
      }
    }
    else
    {
      return 8;
    }
  }
  return v4;
}

```

## disassembly

```asm
0x18004ccf0  mov     [rsp+arg_8], rbx
0x18004ccf5  mov     [rsp+arg_10], rbp
0x18004ccfa  push    rsi
0x18004ccfb  push    rdi
0x18004ccfc  push    r14
0x18004ccfe  sub     rsp, 30h
0x18004cd02  xor     ebp, ebp
0x18004cd04  mov     r14, rdx
0x18004cd07  mov     rdi, rcx
0x18004cd0a  mov     ebx, ebp
0x18004cd0c  test    rcx, rcx
0x18004cd0f  jnz     short loc_18004CD19
0x18004cd11  mov     [rdx], rbp
0x18004cd14  jmp     loc_18004CE1F
0x18004cd19  or      rsi, 0FFFFFFFFFFFFFFFFh
0x18004cd1d  mov     [rsp+48h+BytesInMultiByteString], ebp
0x18004cd21  cmp     dword ptr [rcx+0Ch], 1
0x18004cd25  jnz     short loc_18004CD6D
0x18004cd27  mov     rdx, [rcx+18h]; UnicodeString
0x18004cd2b  mov     r8, rsi
0x18004cd2e  inc     r8
0x18004cd31  cmp     [rdx+r8*2], bp
0x18004cd36  jnz     short loc_18004CD2E
0x18004cd38  lea     r8d, ds:2[r8*2]; BytesInUnicodeString
0x18004cd40  lea     rcx, [rsp+48h+BytesInMultiByteString]; BytesInMultiByteString
0x18004cd45  call    cs:__imp_RtlUnicodeToMultiByteSize
0x18004cd4b  test    eax, eax
0x18004cd4d  jns     short loc_18004CD59
0x18004cd4f  mov     ecx, eax; Status
0x18004cd51  call    cs:__imp_RtlNtStatusToDosErrorNoTeb
0x18004cd57  mov     ebx, eax
0x18004cd59  mov     eax, [rsp+48h+BytesInMultiByteString]
0x18004cd5d  inc     eax
0x18004cd5f  mov     [rsp+48h+BytesInMultiByteString], eax
0x18004cd63  test    ebx, ebx
0x18004cd65  jnz     loc_18004CE1F
0x18004cd6b  jmp     short loc_18004CD9C
0x18004cd6d  cmp     [rcx+0Ch], ebp
0x18004cd70  jnz     loc_18004CE1A
0x18004cd76  mov     rcx, [rcx+18h]; Sid
0x18004cd7a  call    cs:__imp_RtlValidSid
0x18004cd80  test    al, al
0x18004cd82  jnz     short loc_18004CD8E
0x18004cd84  mov     ebx, 539h
0x18004cd89  jmp     loc_18004CE1F
0x18004cd8e  mov     rcx, [rdi+18h]; Sid
0x18004cd92  call    cs:__imp_RtlLengthSid
0x18004cd98  mov     [rsp+48h+BytesInMultiByteString], eax
0x18004cd9c  mov     edx, eax
0x18004cd9e  mov     ecx, 40h ; '@'; uFlags
0x18004cda3  add     rdx, 20h ; ' '; uBytes
0x18004cda7  call    cs:__imp_LocalAlloc
0x18004cdad  mov     [r14], rax
0x18004cdb0  test    rax, rax
0x18004cdb3  jnz     short loc_18004CDBA
0x18004cdb5  lea     ebx, [rax+8]
0x18004cdb8  jmp     short loc_18004CE1F
0x18004cdba  movups  xmm0, xmmword ptr [rdi]
0x18004cdbd  lea     rcx, [rax+20h]; MbString
0x18004cdc1  movups  xmmword ptr [rax], xmm0
0x18004cdc4  movups  xmm1, xmmword ptr [rdi+10h]
0x18004cdc8  movups  xmmword ptr [rax+10h], xmm1
0x18004cdcc  mov     [rax+18h], rcx
0x18004cdd0  cmp     dword ptr [rdi+0Ch], 1
0x18004cdd4  mov     r8, [rdi+18h]; SourceSid
0x18004cdd8  jnz     short loc_18004CE0B
0x18004cdda  inc     rsi
0x18004cddd  cmp     [r8+rsi*2], bp
0x18004cde2  jnz     short loc_18004CDDA
0x18004cde4  lea     edx, ds:2[rsi*2]; MbSize
0x18004cdeb  mov     r9, r8; UnicodeString
0x18004cdee  xor     r8d, r8d; ResultSize
0x18004cdf1  mov     [rsp+48h+UnicodeSize], edx; UnicodeSize
0x18004cdf5  call    cs:__imp_RtlUnicodeToMultiByteN
0x18004cdfb  test    eax, eax
0x18004cdfd  jns     short loc_18004CE1F
0x18004cdff  mov     ecx, eax; Status
0x18004ce01  call    cs:__imp_RtlNtStatusToDosErrorNoTeb
0x18004ce07  mov     ebx, eax
0x18004ce09  jmp     short loc_18004CE1F
0x18004ce0b  mov     rdx, rcx; DestinationSid
0x18004ce0e  mov     ecx, [rsp+48h+BytesInMultiByteString]; DestinationSidLength
0x18004ce12  call    cs:__imp_RtlCopySid
0x18004ce18  jmp     short loc_18004CE1F
0x18004ce1a  mov     ebx, 57h ; 'W'
0x18004ce1f  mov     rbp, [rsp+48h+arg_10]
0x18004ce24  mov     eax, ebx
0x18004ce26  mov     rbx, [rsp+48h+arg_8]
0x18004ce2b  add     rsp, 30h
0x18004ce2f  pop     r14
0x18004ce31  pop     rdi
0x18004ce32  pop     rsi
0x18004ce33  retn
```
