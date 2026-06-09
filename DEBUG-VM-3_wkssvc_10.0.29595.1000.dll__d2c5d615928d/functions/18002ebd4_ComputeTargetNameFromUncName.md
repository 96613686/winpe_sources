# ComputeTargetNameFromUncName

- ea: `0x18002ebd4`
- end: `0x18002ecb8`
- name: `ComputeTargetNameFromUncName`
- size: `228`
- prototype: ``
- caller_count: `4`
- callee_count: `3`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x1800299a4`
- `0x18002eda0`
- `0x18002edfc`
- `0x18002f1b0`

## callees

- `0x18000dd94`
- `0x18002ebd4`
- `0x180033159`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__itow_s` at `0x18002ec8b`
- `api-ms-win-crt-private-l1-1-0!_o__itow_s` at `0x18002ec8b`
- `ntdll!RtlInitUnicodeString` at `0x18002ec4d`
- `ntdll!RtlInitUnicodeString` at `0x18002ec4d`
- `ntdll!RtlHashUnicodeString` at `0x18002ec66`
- `ntdll!RtlHashUnicodeString` at `0x18002ec66`

## pseudocode

```c
__int64 __fastcall ComputeTargetNameFromUncName(_WORD *a1, char *a2)
{
  bool v3; // zf
  const WCHAR *v4; // rsi
  int v5; // edi
  struct _UNICODE_STRING DestinationString; // [rsp+20h] [rbp-38h] BYREF
  ULONG HashValue; // [rsp+60h] [rbp+8h] BYREF

  v3 = *a1 == 92;
  DestinationString = 0;
  HashValue = 0;
  if ( !v3 )
    return 0;
  if ( a1[1] != 92 )
    return 0;
  v4 = a1 + 2;
  if ( !a1[2] )
    return 0;
  v5 = 0;
  do
  {
    if ( v4[v5] == 92 )
      break;
    ++v5;
  }
  while ( v4[v5] );
  if ( v5 > 255 )
    return 0;
  memcpy_0(a2, a1 + 2, 2LL * v5);
  RtlInitUnicodeString(&DestinationString, v4);
  RtlHashUnicodeString(&DestinationString, 1u, 1u, &HashValue);
  *(_WORD *)&a2[2 * v5] = 95;
  _o__itow_s(HashValue, &a2[2 * v5 + 2], 9);
  StringCchCatW((STRSAFE_LPWSTR)a2, 0x151u, L".SMB-GlobalMapping-Target");
  return 1;
}

```

## disassembly

```asm
0x18002ebd4  push    rbx
0x18002ebd6  push    rsi
0x18002ebd7  push    rdi
0x18002ebd8  push    r14
0x18002ebda  sub     rsp, 38h
0x18002ebde  mov     r14, rdx
0x18002ebe1  xorps   xmm0, xmm0
0x18002ebe4  xor     edx, edx
0x18002ebe6  cmp     word ptr [rcx], 5Ch ; '\'
0x18002ebea  movups  xmmword ptr [rsp+58h+DestinationString.Length], xmm0
0x18002ebef  mov     [rsp+58h+HashValue], edx
0x18002ebf3  jnz     loc_18002ECAC
0x18002ebf9  cmp     word ptr [rcx+2], 5Ch ; '\'
0x18002ebfe  jnz     loc_18002ECAC
0x18002ec04  lea     rsi, [rcx+4]
0x18002ec08  cmp     [rsi], dx
0x18002ec0b  jz      loc_18002ECAC
0x18002ec11  mov     edi, edx
0x18002ec13  movsxd  rax, edi
0x18002ec16  cmp     word ptr [rsi+rax*2], 5Ch ; '\'
0x18002ec1b  jz      short loc_18002EC28
0x18002ec1d  inc     edi
0x18002ec1f  movsxd  rax, edi
0x18002ec22  cmp     [rsi+rax*2], dx
0x18002ec26  jnz     short loc_18002EC13
0x18002ec28  cmp     edi, 0FFh
0x18002ec2e  jg      short loc_18002ECAC
0x18002ec30  movsxd  rax, edi
0x18002ec33  mov     rdx, rsi; Src
0x18002ec36  mov     rcx, r14; void *
0x18002ec39  lea     rbx, [rax+rax]
0x18002ec3d  mov     r8, rbx; Size
0x18002ec40  call    memcpy_0
0x18002ec45  mov     rdx, rsi; SourceString
0x18002ec48  lea     rcx, [rsp+58h+DestinationString]; DestinationString
0x18002ec4d  call    cs:__imp_RtlInitUnicodeString
0x18002ec53  mov     r8d, 1; HashAlgorithm
0x18002ec59  lea     r9, [rsp+58h+HashValue]; HashValue
0x18002ec5e  mov     dl, r8b; CaseInSensitive
0x18002ec61  lea     rcx, [rsp+58h+DestinationString]; String
0x18002ec66  call    cs:__imp_RtlHashUnicodeString
0x18002ec6c  lea     ecx, [rdi+1]
0x18002ec6f  mov     word ptr [rbx+r14], 5Fh ; '_'
0x18002ec76  movsxd  rdx, ecx
0x18002ec79  mov     r9d, 10h
0x18002ec7f  mov     ecx, [rsp+58h+HashValue]
0x18002ec83  lea     rdx, [r14+rdx*2]
0x18002ec87  lea     r8d, [r9-7]
0x18002ec8b  call    cs:__imp__o__itow_s
0x18002ec91  lea     r8, aSmbGlobalmappi; ".SMB-GlobalMapping-Target"
0x18002ec98  mov     edx, 151h; cchDest
0x18002ec9d  mov     rcx, r14; pszDest
0x18002eca0  call    StringCchCatW
0x18002eca5  mov     eax, 1
0x18002ecaa  jmp     short loc_18002ECAE
0x18002ecac  xor     eax, eax
0x18002ecae  add     rsp, 38h
0x18002ecb2  pop     r14
0x18002ecb4  pop     rdi
0x18002ecb5  pop     rsi
0x18002ecb6  pop     rbx
0x18002ecb7  retn
```
