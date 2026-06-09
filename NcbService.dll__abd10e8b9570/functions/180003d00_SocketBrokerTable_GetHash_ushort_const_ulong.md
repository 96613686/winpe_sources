# SocketBrokerTable::GetHash(ushort const *,ulong *)

- ea: `0x180003d00`
- end: `0x180003ec1`
- name: `?GetHash@SocketBrokerTable@@AEAAKPEBGPEAK@Z`
- size: `449`
- prototype: `__int64 __fastcall(SocketBrokerTable *this, const unsigned __int16 *, unsigned int *)`
- caller_count: `3`
- callee_count: `4`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x1800039a0`
- `0x180003b60`
- `0x1800261d8`

## callees

- `0x180003d00`
- `0x180003ed0`
- `0x1800050d0`
- `0x18000a0a0`

## import_xrefs

- `ntdll!RtlInitUnicodeString` at `0x180003ddd`
- `ntdll!RtlInitUnicodeString` at `0x180003ddd`
- `ntdll!RtlNtStatusToDosError` at `0x180003e96`
- `ntdll!RtlNtStatusToDosError` at `0x180003e96`
- `ntdll!RtlHashUnicodeString` at `0x180003df3`
- `ntdll!RtlHashUnicodeString` at `0x180003df3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180003e6c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180003e6c`

## string_xrefs

- `0x180003e26`: `NcbUtilsAllocCopyString: Overflow in caluclating string length. ULongAdd failed`
- `0x180003eb5`: `NcbUtilsAllocCopyString: Overflow in caluclating string length. ULongMult failed`
- `0x180003e84`: `NcbUtilsAllocCopyString: Failed to allocate memory`
- `0x180003e54`: `NcbUtilsAllocCopyString: StringCchCopyW failed`

## pseudocode

```c
__int64 __fastcall SocketBrokerTable::GetHash(SocketBrokerTable *this, const unsigned __int16 *a2, unsigned int *a3)
{
  _WORD *v5; // rsi
  __int64 v6; // rax
  __int64 v7; // rcx
  unsigned __int64 v8; // rax
  unsigned __int64 v9; // rdi
  _WORD *v10; // rax
  _WORD *v11; // rcx
  ULONG v12; // ebx
  __int64 v13; // rax
  const unsigned __int16 *v14; // rcx
  _WORD *v15; // r8
  __int64 v16; // rdx
  int v17; // eax
  const wchar_t *v19; // r8
  __int64 v20; // r9
  const wchar_t *v21; // r8
  DWORD LastError; // eax
  _UNICODE_STRING DestinationString; // [rsp+20h] [rbp-48h] BYREF

  v5 = 0;
  DestinationString = 0;
  if ( !a2 )
  {
    v12 = 87;
    goto LABEL_19;
  }
  v6 = -1;
  do
    ++v6;
  while ( a2[v6] );
  v7 = (unsigned int)(v6 + 1);
  if ( (unsigned int)v7 < (unsigned int)v6 )
  {
    v12 = 534;
    if ( (Microsoft_Windows_Network_Connection_BrokerEnableBits & 1) == 0 )
      goto LABEL_19;
    v19 = L"NcbUtilsAllocCopyString: Overflow in caluclating string length. ULongAdd failed";
LABEL_22:
    McTemplateU0zq_EventWriteTransfer(v7, a2, v19, 534);
    goto LABEL_19;
  }
  v8 = 2 * v7;
  v9 = (unsigned int)v7;
  v7 = 0xFFFFFFFFLL;
  if ( v8 > 0xFFFFFFFF )
  {
    v12 = 534;
    if ( (Microsoft_Windows_Network_Connection_BrokerEnableBits & 1) == 0 )
      goto LABEL_19;
    v19 = L"NcbUtilsAllocCopyString: Overflow in caluclating string length. ULongMult failed";
    goto LABEL_22;
  }
  v10 = (_WORD *)MALLOC((unsigned int)v8);
  v5 = v10;
  if ( !v10 )
  {
    LastError = GetLastError();
    v12 = LastError;
    if ( (Microsoft_Windows_Network_Connection_BrokerEnableBits & 1) == 0 )
      goto LABEL_16;
    v20 = LastError;
    v21 = L"NcbUtilsAllocCopyString: Failed to allocate memory";
    goto LABEL_26;
  }
  if ( v9 )
  {
    if ( v9 > 0x7FFFFFFF )
    {
      v16 = 2147942487LL;
      *v10 = 0;
    }
    else
    {
      v12 = 0;
      v13 = 2147483646;
      v14 = a2;
      v15 = v5;
      do
      {
        if ( !v13 )
          break;
        if ( !*v14 )
          break;
        *v15++ = *v14++;
        --v13;
        --v9;
      }
      while ( v9 );
      v11 = v15 - 1;
      v16 = v9 == 0 ? 0x8007007A : 0;
      if ( v9 )
        v11 = v15;
      *v11 = 0;
      if ( v9 )
        goto LABEL_16;
    }
  }
  else
  {
    v16 = 2147942487LL;
  }
  v12 = (unsigned __int16)v16;
  if ( (Microsoft_Windows_Network_Connection_BrokerEnableBits & 1) != 0 )
  {
    v20 = (unsigned __int16)v16;
    v21 = L"NcbUtilsAllocCopyString: StringCchCopyW failed";
LABEL_26:
    McTemplateU0zq_EventWriteTransfer(v11, v16, v21, v20);
  }
LABEL_16:
  if ( !v12 )
  {
    RtlInitUnicodeString(&DestinationString, a2);
    *a3 = 0;
    v17 = RtlHashUnicodeString(&DestinationString, 1u, 0, a3);
    if ( v17 < 0 )
      v12 = RtlNtStatusToDosError(v17);
  }
LABEL_19:
  VpnFree(v5);
  return v12;
}

```

## disassembly

```asm
0x180003d00  push    rbx
0x180003d02  push    rbp
0x180003d03  push    rsi
0x180003d04  push    rdi
0x180003d05  push    r14
0x180003d07  push    r15
0x180003d09  sub     rsp, 38h
0x180003d0d  xor     r15d, r15d
0x180003d10  xorps   xmm0, xmm0
0x180003d13  mov     r14, r8
0x180003d16  mov     rbp, rdx
0x180003d19  mov     esi, r15d
0x180003d1c  movups  xmmword ptr [rsp+68h+DestinationString.Length], xmm0
0x180003d21  test    rdx, rdx
0x180003d24  jz      loc_180003E65
0x180003d2a  or      rax, 0FFFFFFFFFFFFFFFFh
0x180003d2e  inc     rax
0x180003d31  cmp     [rdx+rax*2], r15w
0x180003d36  jnz     short loc_180003D2E
0x180003d38  lea     ecx, [rax+1]
0x180003d3b  cmp     ecx, eax
0x180003d3d  jb      loc_180003E18
0x180003d43  lea     rax, [rcx+rcx]
0x180003d47  mov     edi, ecx
0x180003d49  mov     ecx, 0FFFFFFFFh
0x180003d4e  cmp     rax, rcx
0x180003d51  ja      loc_180003EA3
0x180003d57  mov     ecx, eax; dwBytes
0x180003d59  call    MALLOC
0x180003d5e  mov     rsi, rax
0x180003d61  test    rax, rax
0x180003d64  jz      loc_180003E6C
0x180003d6a  test    rdi, rdi
0x180003d6d  jz      loc_180003E37
0x180003d73  cmp     rdi, 7FFFFFFFh
0x180003d7a  ja      loc_180003E8D
0x180003d80  mov     ebx, r15d
0x180003d83  mov     eax, 7FFFFFFEh
0x180003d88  mov     rcx, rbp
0x180003d8b  mov     r8, rsi
0x180003d8e  test    rax, rax
0x180003d91  jz      short loc_180003DB0
0x180003d93  movzx   edx, word ptr [rcx]
0x180003d96  test    dx, dx
0x180003d99  jz      short loc_180003DB0
0x180003d9b  mov     [r8], dx
0x180003d9f  add     rcx, 2
0x180003da3  add     r8, 2
0x180003da7  dec     rax
0x180003daa  sub     rdi, 1
0x180003dae  jnz     short loc_180003D8E
0x180003db0  mov     rax, rdi
0x180003db3  lea     rcx, [r8-2]
0x180003db7  neg     rax
0x180003dba  sbb     edx, edx
0x180003dbc  not     edx
0x180003dbe  and     edx, 8007007Ah
0x180003dc4  test    rdi, rdi
0x180003dc7  cmovnz  rcx, r8
0x180003dcb  mov     [rcx], r15w
0x180003dcf  jz      short loc_180003E45
0x180003dd1  test    ebx, ebx
0x180003dd3  jnz     short loc_180003E01
0x180003dd5  mov     rdx, rbp; SourceString
0x180003dd8  lea     rcx, [rsp+68h+DestinationString]; DestinationString
0x180003ddd  call    cs:__imp_RtlInitUnicodeString
0x180003de3  mov     r9, r14; HashValue
0x180003de6  mov     [r14], r15d
0x180003de9  xor     r8d, r8d; HashAlgorithm
0x180003dec  lea     rcx, [rsp+68h+DestinationString]; String
0x180003df1  mov     dl, 1; CaseInSensitive
0x180003df3  call    cs:__imp_RtlHashUnicodeString
0x180003df9  test    eax, eax
0x180003dfb  js      loc_180003E94
0x180003e01  mov     rcx, rsi; lpMem
0x180003e04  call    VpnFree
0x180003e09  mov     eax, ebx
0x180003e0b  add     rsp, 38h
0x180003e0f  pop     r15
0x180003e11  pop     r14
0x180003e13  pop     rdi
0x180003e14  pop     rsi
0x180003e15  pop     rbp
0x180003e16  pop     rbx
0x180003e17  retn
0x180003e18  test    byte ptr cs:Microsoft_Windows_Network_Connection_BrokerEnableBits, 1
0x180003e1f  mov     ebx, 216h
0x180003e24  jz      short loc_180003E01
0x180003e26  lea     r8, aNcbutilsallocc_3; "NcbUtilsAllocCopyString: Overflow in ca"...
0x180003e2d  mov     r9d, ebx
0x180003e30  call    McTemplateU0zq_EventWriteTransfer
0x180003e35  jmp     short loc_180003E01
0x180003e37  mov     edx, 80070057h
0x180003e3c  test    rdi, rdi
0x180003e3f  jz      short loc_180003E45
0x180003e41  mov     [rax], r15w
0x180003e45  test    byte ptr cs:Microsoft_Windows_Network_Connection_BrokerEnableBits, 1
0x180003e4c  movzx   ebx, dx
0x180003e4f  jz      short loc_180003DD1
0x180003e51  mov     r9d, ebx
0x180003e54  lea     r8, aNcbutilsallocc_1; "NcbUtilsAllocCopyString: StringCchCopyW"...
0x180003e5b  call    McTemplateU0zq_EventWriteTransfer
0x180003e60  jmp     loc_180003DD1
0x180003e65  mov     ebx, 57h ; 'W'
0x180003e6a  jmp     short loc_180003E01
0x180003e6c  call    cs:__imp_GetLastError
0x180003e72  test    byte ptr cs:Microsoft_Windows_Network_Connection_BrokerEnableBits, 1
0x180003e79  mov     ebx, eax
0x180003e7b  jz      loc_180003DD1
0x180003e81  mov     r9d, eax
0x180003e84  lea     r8, aNcbutilsallocc_0; "NcbUtilsAllocCopyString: Failed to allo"...
0x180003e8b  jmp     short loc_180003E5B
0x180003e8d  mov     edx, 80070057h
0x180003e92  jmp     short loc_180003E41
0x180003e94  mov     ecx, eax; Status
0x180003e96  call    cs:__imp_RtlNtStatusToDosError
0x180003e9c  mov     ebx, eax
0x180003e9e  jmp     loc_180003E01
0x180003ea3  test    byte ptr cs:Microsoft_Windows_Network_Connection_BrokerEnableBits, 1
0x180003eaa  mov     ebx, 216h
0x180003eaf  jz      loc_180003E01
0x180003eb5  lea     r8, aNcbutilsallocc_2; "NcbUtilsAllocCopyString: Overflow in ca"...
0x180003ebc  jmp     loc_180003E2D
```
