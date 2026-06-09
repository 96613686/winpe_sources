# ConvertTrusteeWToTrusteeA(_TRUSTEE_W *,_TRUSTEE_A * *)

- ea: `0x180052cac`
- end: `0x180052e21`
- name: `?ConvertTrusteeWToTrusteeA@@YAKPEAU_TRUSTEE_W@@PEAPEAU_TRUSTEE_A@@@Z`
- size: `373`
- prototype: `unsigned int __fastcall(struct _TRUSTEE_W *, struct _TRUSTEE_A **)`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, loader_planting`

## callers

- `0x18004ee00`

## callees

- `0x180052cac`

## import_xrefs

- `ntdll!RtlLengthSid` at `0x180052d60`
- `ntdll!RtlLengthSid` at `0x180052d60`
- `ntdll!RtlValidSid` at `0x180052d42`
- `ntdll!RtlValidSid` at `0x180052d42`
- `ntdll!RtlCopySid` at `0x180052df8`
- `ntdll!RtlCopySid` at `0x180052df8`
- `ntdll!RtlUnicodeToMultiByteN` at `0x180052dcf`
- `ntdll!RtlUnicodeToMultiByteN` at `0x180052dcf`
- `ntdll!RtlNtStatusToDosErrorNoTeb` at `0x180052d13`
- `ntdll!RtlNtStatusToDosErrorNoTeb` at `0x180052de1`
- `ntdll!RtlNtStatusToDosErrorNoTeb` at `0x180052d13`
- `ntdll!RtlNtStatusToDosErrorNoTeb` at `0x180052de1`
- `ntdll!RtlUnicodeToMultiByteSize` at `0x180052d01`
- `ntdll!RtlUnicodeToMultiByteSize` at `0x180052d01`
- `KERNELBASE!LocalAlloc` at `0x180052d7b`
- `KERNELBASE!LocalAlloc` at `0x180052d7b`

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
0x180052cac  mov     [rsp+arg_8], rbx
0x180052cb1  mov     [rsp+arg_10], rbp
0x180052cb6  push    rsi
0x180052cb7  push    rdi
0x180052cb8  push    r14
0x180052cba  sub     rsp, 30h
0x180052cbe  xor     ebp, ebp
0x180052cc0  mov     r14, rdx
0x180052cc3  mov     rdi, rcx
0x180052cc6  mov     ebx, ebp
0x180052cc8  test    rcx, rcx
0x180052ccb  jnz     short loc_180052CD5
0x180052ccd  mov     [rdx], rbp
0x180052cd0  jmp     loc_180052E0B
0x180052cd5  or      rsi, 0FFFFFFFFFFFFFFFFh
0x180052cd9  mov     [rsp+48h+BytesInMultiByteString], ebp
0x180052cdd  cmp     dword ptr [rcx+0Ch], 1
0x180052ce1  jnz     short loc_180052D35
0x180052ce3  mov     rdx, [rcx+18h]; UnicodeString
0x180052ce7  mov     r8, rsi
0x180052cea  inc     r8
0x180052ced  cmp     [rdx+r8*2], bp
0x180052cf2  jnz     short loc_180052CEA
0x180052cf4  lea     r8d, ds:2[r8*2]; BytesInUnicodeString
0x180052cfc  lea     rcx, [rsp+48h+BytesInMultiByteString]; BytesInMultiByteString
0x180052d01  call    cs:__imp_RtlUnicodeToMultiByteSize
0x180052d08  nop     dword ptr [rax+rax+00h]
0x180052d0d  test    eax, eax
0x180052d0f  jns     short loc_180052D21
0x180052d11  mov     ecx, eax; Status
0x180052d13  call    cs:__imp_RtlNtStatusToDosErrorNoTeb
0x180052d1a  nop     dword ptr [rax+rax+00h]
0x180052d1f  mov     ebx, eax
0x180052d21  mov     eax, [rsp+48h+BytesInMultiByteString]
0x180052d25  inc     eax
0x180052d27  mov     [rsp+48h+BytesInMultiByteString], eax
0x180052d2b  test    ebx, ebx
0x180052d2d  jnz     loc_180052E0B
0x180052d33  jmp     short loc_180052D70
0x180052d35  cmp     [rcx+0Ch], ebp
0x180052d38  jnz     loc_180052E06
0x180052d3e  mov     rcx, [rcx+18h]; Sid
0x180052d42  call    cs:__imp_RtlValidSid
0x180052d49  nop     dword ptr [rax+rax+00h]
0x180052d4e  test    al, al
0x180052d50  jnz     short loc_180052D5C
0x180052d52  mov     ebx, 539h
0x180052d57  jmp     loc_180052E0B
0x180052d5c  mov     rcx, [rdi+18h]; Sid
0x180052d60  call    cs:__imp_RtlLengthSid
0x180052d67  nop     dword ptr [rax+rax+00h]
0x180052d6c  mov     [rsp+48h+BytesInMultiByteString], eax
0x180052d70  mov     edx, eax
0x180052d72  mov     ecx, 40h ; '@'; uFlags
0x180052d77  add     rdx, 20h ; ' '; uBytes
0x180052d7b  call    cs:__imp_LocalAlloc
0x180052d82  nop     dword ptr [rax+rax+00h]
0x180052d87  mov     [r14], rax
0x180052d8a  test    rax, rax
0x180052d8d  jnz     short loc_180052D94
0x180052d8f  lea     ebx, [rax+8]
0x180052d92  jmp     short loc_180052E0B
0x180052d94  movups  xmm0, xmmword ptr [rdi]
0x180052d97  lea     rcx, [rax+20h]; MbString
0x180052d9b  movups  xmmword ptr [rax], xmm0
0x180052d9e  movups  xmm1, xmmword ptr [rdi+10h]
0x180052da2  movups  xmmword ptr [rax+10h], xmm1
0x180052da6  mov     [rax+18h], rcx
0x180052daa  cmp     dword ptr [rdi+0Ch], 1
0x180052dae  mov     r8, [rdi+18h]; SourceSid
0x180052db2  jnz     short loc_180052DF1
0x180052db4  inc     rsi
0x180052db7  cmp     [r8+rsi*2], bp
0x180052dbc  jnz     short loc_180052DB4
0x180052dbe  lea     edx, ds:2[rsi*2]; MbSize
0x180052dc5  mov     r9, r8; UnicodeString
0x180052dc8  xor     r8d, r8d; ResultSize
0x180052dcb  mov     [rsp+48h+UnicodeSize], edx; UnicodeSize
0x180052dcf  call    cs:__imp_RtlUnicodeToMultiByteN
0x180052dd6  nop     dword ptr [rax+rax+00h]
0x180052ddb  test    eax, eax
0x180052ddd  jns     short loc_180052E0B
0x180052ddf  mov     ecx, eax; Status
0x180052de1  call    cs:__imp_RtlNtStatusToDosErrorNoTeb
0x180052de8  nop     dword ptr [rax+rax+00h]
0x180052ded  mov     ebx, eax
0x180052def  jmp     short loc_180052E0B
0x180052df1  mov     rdx, rcx; DestinationSid
0x180052df4  mov     ecx, [rsp+48h+BytesInMultiByteString]; DestinationSidLength
0x180052df8  call    cs:__imp_RtlCopySid
0x180052dff  nop     dword ptr [rax+rax+00h]
0x180052e04  jmp     short loc_180052E0B
0x180052e06  mov     ebx, 57h ; 'W'
0x180052e0b  mov     rbp, [rsp+48h+arg_10]
0x180052e10  mov     eax, ebx
0x180052e12  mov     rbx, [rsp+48h+arg_8]
0x180052e17  add     rsp, 30h
0x180052e1b  pop     r14
0x180052e1d  pop     rdi
0x180052e1e  pop     rsi
0x180052e1f  retn
```
