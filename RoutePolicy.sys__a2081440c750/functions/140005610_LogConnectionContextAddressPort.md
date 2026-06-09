# LogConnectionContextAddressPort

- ea: `0x140005610`
- end: `0x14000586e`
- name: `LogConnectionContextAddressPort`
- size: `606`
- prototype: ``
- caller_count: `3`
- callee_count: `4`
- tags: ``

## callers

- `0x1400037a4`
- `0x140004a84`
- `0x140006afc`

## callees

- `0x1400012f0`
- `0x140005610`
- `0x14000a680`
- `0x14000aa80`

## import_xrefs

- `ntoskrnl!RtlIpv6AddressToStringExW` at `0x1400056fd`
- `ntoskrnl!RtlIpv6AddressToStringExW` at `0x140005731`
- `ntoskrnl!RtlIpv6AddressToStringExW` at `0x1400056fd`
- `ntoskrnl!RtlIpv6AddressToStringExW` at `0x140005731`
- `ntoskrnl!RtlIpv4AddressToStringExW` at `0x1400056a7`
- `ntoskrnl!RtlIpv4AddressToStringExW` at `0x1400056d6`
- `ntoskrnl!RtlIpv4AddressToStringExW` at `0x1400056a7`
- `ntoskrnl!RtlIpv4AddressToStringExW` at `0x1400056d6`

## pseudocode

```c
NTSTATUS __fastcall LogConnectionContextAddressPort(int *a1, __int16 *a2, __int16 *a3, char a4)
{
  __int16 v8; // r14
  USHORT v9; // ax
  USHORT v10; // dx
  USHORT v11; // r8
  ULONG v12; // edx
  NTSTATUS result; // eax
  int v14; // r8d
  const wchar_t *v15; // rdx
  __int64 v16; // rcx
  __int64 v17; // rax
  __int64 v18; // rax
  __int64 v19; // rax
  char v20; // [rsp+30h] [rbp-D0h] BYREF
  ULONG AddressStringLength[3]; // [rsp+34h] [rbp-CCh] BYREF
  struct _EVENT_DATA_DESCRIPTOR v22; // [rsp+40h] [rbp-C0h] BYREF
  int *v23; // [rsp+60h] [rbp-A0h]
  int v24; // [rsp+68h] [rbp-98h]
  int v25; // [rsp+6Ch] [rbp-94h]
  const wchar_t *v26; // [rsp+70h] [rbp-90h]
  int v27; // [rsp+78h] [rbp-88h]
  int v28; // [rsp+7Ch] [rbp-84h]
  WCHAR *v29; // [rsp+80h] [rbp-80h]
  int v30; // [rsp+88h] [rbp-78h]
  int v31; // [rsp+8Ch] [rbp-74h]
  WCHAR *v32; // [rsp+90h] [rbp-70h]
  int v33; // [rsp+98h] [rbp-68h]
  int v34; // [rsp+9Ch] [rbp-64h]
  char *v35; // [rsp+A0h] [rbp-60h]
  __int64 v36; // [rsp+A8h] [rbp-58h]
  WCHAR v37[72]; // [rsp+B0h] [rbp-50h] BYREF
  WCHAR AddressString[72]; // [rsp+140h] [rbp+40h] BYREF

  memset(AddressString, 0, 0x82u);
  memset(v37, 0, 0x82u);
  v8 = *a3;
  AddressStringLength[0] = 65;
  if ( !v8 )
    v8 = *a2;
  v9 = a2[1];
  if ( v8 == 2 )
  {
    RtlIpv4AddressToStringExW((const struct in_addr *)a2 + 1, v9, AddressString, AddressStringLength);
    if ( *a3 )
    {
      v10 = a3[1];
      AddressStringLength[0] = 65;
      RtlIpv4AddressToStringExW((const struct in_addr *)a3 + 1, v10, v37, AddressStringLength);
    }
  }
  else
  {
    RtlIpv6AddressToStringExW(
      (const struct in6_addr *)(a2 + 4),
      *((_DWORD *)a2 + 6),
      v9,
      AddressString,
      AddressStringLength);
    if ( *a3 )
    {
      v11 = a3[1];
      v12 = *((_DWORD *)a3 + 6);
      AddressStringLength[0] = 65;
      RtlIpv6AddressToStringExW((const struct in6_addr *)(a3 + 4), v12, v11, v37, AddressStringLength);
    }
  }
  result = dword_140012050;
  if ( (unsigned int)dword_140012050 > 4 )
  {
    v20 = a4;
    v14 = 1;
    v15 = L"IPv4";
    v36 = 1;
    if ( v8 != 2 )
      v15 = L"IPv6";
    v16 = -1;
    v35 = &v20;
    v17 = -1;
    do
      ++v17;
    while ( v37[v17] );
    v34 = 0;
    v32 = v37;
    v33 = 2 * v17 + 2;
    v18 = -1;
    do
      ++v18;
    while ( AddressString[v18] );
    v31 = 0;
    v30 = 2 * v18 + 2;
    v19 = -1;
    v29 = AddressString;
    do
      ++v19;
    while ( v15[v19] );
    v26 = v15;
    v27 = 2 * v19 + 2;
    v28 = 0;
    if ( a1 )
    {
      do
        ++v16;
      while ( *((_BYTE *)a1 + v16) );
      v14 = v16 + 1;
    }
    else
    {
      a1 = &dword_14000C864;
    }
    v24 = v14;
    v23 = a1;
    v25 = 0;
    return tlgWriteTransfer_EtwWriteTransfer(
             (__int64)&dword_140012050,
             (unsigned __int8 *)&word_14000F082,
             0,
             0,
             7u,
             &v22);
  }
  return result;
}

```

## disassembly

```asm
0x140005610  mov     [rsp-8+arg_0], rbx
0x140005615  push    rbp
0x140005616  push    rsi
0x140005617  push    rdi
0x140005618  push    r12
0x14000561a  push    r13
0x14000561c  push    r14
0x14000561e  push    r15
0x140005620  lea     rbp, [rsp-0E0h]
0x140005628  sub     rsp, 1E0h
0x14000562f  mov     rax, cs:__security_cookie
0x140005636  xor     rax, rsp
0x140005639  mov     [rbp+110h+var_40], rax
0x140005640  mov     rbx, r8
0x140005643  mov     rdi, rdx
0x140005646  mov     rsi, rcx
0x140005649  mov     r14d, 82h
0x14000564f  mov     r8d, r14d; Size
0x140005652  lea     rcx, [rbp+110h+AddressString]; void *
0x140005656  xor     edx, edx; Val
0x140005658  mov     r15b, r9b
0x14000565b  call    memset
0x140005660  mov     r8d, r14d; Size
0x140005663  lea     rcx, [rbp+110h+var_160]; void *
0x140005667  xor     edx, edx; Val
0x140005669  call    memset
0x14000566e  movzx   r14d, word ptr [rbx]
0x140005672  xor     r12d, r12d
0x140005675  mov     [rsp+210h+AddressStringLength], 41h ; 'A'
0x14000567d  cmp     r12w, r14w
0x140005681  jnz     short loc_140005687
0x140005683  movzx   r14d, word ptr [rdi]
0x140005687  movzx   eax, word ptr [rdi+2]
0x14000568b  mov     r13d, 2
0x140005691  cmp     r13w, r14w
0x140005695  jnz     short loc_1400056E4
0x140005697  lea     rcx, [rdi+4]; Address
0x14000569b  movzx   edx, ax; Port
0x14000569e  lea     r9, [rsp+210h+AddressStringLength]; AddressStringLength
0x1400056a3  lea     r8, [rbp+110h+AddressString]; AddressString
0x1400056a7  call    cs:__imp_RtlIpv4AddressToStringExW
0x1400056ae  nop     dword ptr [rax+rax+00h]
0x1400056b3  cmp     r12w, [rbx]
0x1400056b7  jz      loc_14000573D
0x1400056bd  movzx   edx, word ptr [rbx+2]; Port
0x1400056c1  lea     rcx, [rbx+4]; Address
0x1400056c5  lea     r9, [rsp+210h+AddressStringLength]; AddressStringLength
0x1400056ca  mov     [rsp+210h+AddressStringLength], 41h ; 'A'
0x1400056d2  lea     r8, [rbp+110h+var_160]; AddressString
0x1400056d6  call    cs:__imp_RtlIpv4AddressToStringExW
0x1400056dd  nop     dword ptr [rax+rax+00h]
0x1400056e2  jmp     short loc_14000573D
0x1400056e4  lea     rdx, [rsp+210h+AddressStringLength]
0x1400056e9  movzx   r8d, ax; Port
0x1400056ed  mov     [rsp+210h+var_1F0], rdx; AddressStringLength
0x1400056f2  lea     rcx, [rdi+8]; Address
0x1400056f6  mov     edx, [rdi+18h]; ScopeId
0x1400056f9  lea     r9, [rbp+110h+AddressString]; AddressString
0x1400056fd  call    cs:__imp_RtlIpv6AddressToStringExW
0x140005704  nop     dword ptr [rax+rax+00h]
0x140005709  cmp     r12w, [rbx]
0x14000570d  jz      short loc_14000573D
0x14000570f  movzx   r8d, word ptr [rbx+2]; Port
0x140005714  lea     rax, [rsp+210h+AddressStringLength]
0x140005719  mov     edx, [rbx+18h]; ScopeId
0x14000571c  lea     rcx, [rbx+8]; Address
0x140005720  lea     r9, [rbp+110h+var_160]; AddressString
0x140005724  mov     [rsp+210h+var_1F0], rax; AddressStringLength
0x140005729  mov     [rsp+210h+AddressStringLength], 41h ; 'A'
0x140005731  call    cs:__imp_RtlIpv6AddressToStringExW
0x140005738  nop     dword ptr [rax+rax+00h]
0x14000573d  mov     eax, cs:dword_140012050
0x140005743  cmp     eax, 4
0x140005746  jbe     loc_140005843
0x14000574c  cmp     r14w, r13w
0x140005750  mov     [rsp+210h+var_1E0], r15b
0x140005755  lea     rax, aIpv6; "IPv6"
0x14000575c  mov     r8d, 1
0x140005762  lea     rdx, aIpv4; "IPv4"
0x140005769  mov     [rbp+110h+var_168], r8
0x14000576d  cmovnz  rdx, rax
0x140005771  lea     r9, [rbp+110h+var_160]
0x140005775  lea     rax, [rsp+210h+var_1E0]
0x14000577a  or      rcx, 0FFFFFFFFFFFFFFFFh
0x14000577e  mov     [rbp+110h+var_170], rax
0x140005782  mov     rax, rcx
0x140005785  inc     rax
0x140005788  cmp     [r9+rax*2], r12w
0x14000578d  jnz     short loc_140005785
0x14000578f  lea     r9, [rbp+110h+var_160]
0x140005793  mov     [rbp+110h+var_174], r12d
0x140005797  lea     eax, ds:2[rax*2]
0x14000579e  mov     [rbp+110h+var_180], r9
0x1400057a2  mov     [rbp+110h+var_178], eax
0x1400057a5  lea     r9, [rbp+110h+AddressString]
0x1400057a9  mov     rax, rcx
0x1400057ac  inc     rax
0x1400057af  cmp     [r9+rax*2], r12w
0x1400057b4  jnz     short loc_1400057AC
0x1400057b6  lea     eax, ds:2[rax*2]
0x1400057bd  mov     [rbp+110h+var_184], r12d
0x1400057c1  lea     r9, [rbp+110h+AddressString]
0x1400057c5  mov     [rbp+110h+var_188], eax
0x1400057c8  mov     rax, rcx
0x1400057cb  mov     [rbp+110h+var_190], r9
0x1400057cf  inc     rax
0x1400057d2  cmp     [rdx+rax*2], r12w
0x1400057d7  jnz     short loc_1400057CF
0x1400057d9  mov     [rsp+210h+var_1A0], rdx
0x1400057de  lea     eax, ds:2[rax*2]
0x1400057e5  mov     [rsp+210h+var_198], eax
0x1400057e9  mov     [rsp+210h+var_194], r12d
0x1400057ee  test    rsi, rsi
0x1400057f1  jz      short loc_140005802
0x1400057f3  inc     rcx
0x1400057f6  cmp     [rsi+rcx], r12b
0x1400057fa  jnz     short loc_1400057F3
0x1400057fc  lea     r8d, [rcx+1]
0x140005800  jmp     short loc_140005809
0x140005802  lea     rsi, dword_14000C864
0x140005809  lea     rax, [rsp+210h+var_1D0]
0x14000580e  mov     [rsp+210h+var_1A8], r8d
0x140005813  mov     [rsp+210h+var_1E8], rax; PEVENT_DATA_DESCRIPTOR
0x140005818  lea     rdx, word_14000F082; int
0x14000581f  xor     r9d, r9d; int
0x140005822  mov     dword ptr [rsp+210h+var_1F0], 7; ULONG
0x14000582a  xor     r8d, r8d; int
0x14000582d  mov     [rsp+210h+var_1B0], rsi
0x140005832  lea     rcx, dword_140012050; int
0x140005839  mov     [rsp+210h+var_1A4], r12d
0x14000583e  call    _tlgWriteTransfer_EtwWriteTransfer
0x140005843  mov     rcx, [rbp+110h+var_40]
0x14000584a  xor     rcx, rsp; StackCookie
0x14000584d  call    __security_check_cookie
0x140005852  mov     rbx, [rsp+210h+arg_0]
0x14000585a  add     rsp, 1E0h
0x140005861  pop     r15
0x140005863  pop     r14
0x140005865  pop     r13
0x140005867  pop     r12
0x140005869  pop     rdi
0x14000586a  pop     rsi
0x14000586b  pop     rbp
0x14000586c  retn
```
