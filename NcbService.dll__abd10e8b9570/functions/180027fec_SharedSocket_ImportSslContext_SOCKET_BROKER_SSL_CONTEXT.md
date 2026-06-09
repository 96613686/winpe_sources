# SharedSocket::ImportSslContext(_SOCKET_BROKER_SSL_CONTEXT *)

- ea: `0x180027fec`
- end: `0x1800281c7`
- name: `?ImportSslContext@SharedSocket@@AEAAKPEAU_SOCKET_BROKER_SSL_CONTEXT@@@Z`
- size: `475`
- prototype: `__int64 __fastcall(struct _RTL_CRITICAL_SECTION *this, struct _SOCKET_BROKER_SSL_CONTEXT *)`
- caller_count: `1`
- callee_count: `7`
- tags: `file_ops, broker_com_uri`

## callers

- `0x180012490`

## callees

- `0x1800028cc`
- `0x18000a0a0`
- `0x180012900`
- `0x180014130`
- `0x180027fec`
- `0x180032108`
- `0x180033010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180028014`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180028014`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180028056`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180028056`
- `SspiCli!InitSecurityInterfaceW` at `0x180028023`
- `SspiCli!InitSecurityInterfaceW` at `0x180028023`

## string_xrefs

- `0x180028046`: `SharedSocket: InitSecurityInterfaceW failed with`
- `0x180028070`: `SharedSocket:InitializeSecurityFunctions failed`
- `0x1800280a9`: `SharedSocket:ImportSslContext copy string for package name failed`
- `0x1800281ab`: `SharedSocket:ImportSecurityContext failed`

## pseudocode

```c
__int64 __fastcall SharedSocket::ImportSslContext(
        struct _RTL_CRITICAL_SECTION *this,
        struct _SOCKET_BROKER_SSL_CONTEXT *a2)
{
  unsigned int v2; // ebx
  PSecurityFunctionTableW inited; // rax
  __int64 v6; // rdx
  __int64 v7; // rcx
  __int64 v8; // rdx
  void *v9; // rcx
  __int64 v10; // r9
  const wchar_t *v11; // r8
  unsigned int v12; // eax
  bool v13; // zf
  void *v14; // rax
  unsigned int v15; // eax
  void *v16; // rax
  unsigned int v17; // eax
  _OWORD v19[3]; // [rsp+30h] [rbp-38h] BYREF

  v2 = 0;
  v19[0] = 0;
  if ( !a2 )
    return v2;
  EnterCriticalSection(this + 1);
  if ( !this[5].OwningThread )
  {
    inited = InitSecurityInterfaceW();
    this[5].OwningThread = inited;
    if ( !inited )
    {
      v2 = 5023;
      if ( (Microsoft_Windows_Network_Connection_BrokerEnableBits & 1) != 0 )
        McTemplateU0zq_EventWriteTransfer(v7, v6, L"SharedSocket: InitSecurityInterfaceW failed with", 5023);
    }
  }
  LeaveCriticalSection(this + 1);
  if ( v2 )
  {
    if ( (Microsoft_Windows_Network_Connection_BrokerEnableBits & 1) != 0 )
    {
      v10 = v2;
      v11 = L"SharedSocket:InitializeSecurityFunctions failed";
LABEL_28:
      McTemplateU0zq_EventWriteTransfer(v9, v8, v11, v10);
      return v2;
    }
    return v2;
  }
  SharedSocket::FreeSslContext((SharedSocket *)this);
  v12 = NcbUtilsAllocCopyString(*(_QWORD *)a2, &this[3].OwningThread);
  v2 = v12;
  if ( v12 )
  {
    if ( (Microsoft_Windows_Network_Connection_BrokerEnableBits & 1) == 0 )
      return v2;
    v11 = L"SharedSocket:ImportSslContext copy string for package name failed";
    goto LABEL_27;
  }
  v13 = *((_QWORD *)a2 + 4) == 0;
  v19[0] = *(_OWORD *)((char *)a2 + 8);
  if ( v13 || !*((_DWORD *)a2 + 6) )
  {
LABEL_18:
    if ( *((_QWORD *)a2 + 5) && *((_DWORD *)a2 + 7) )
    {
      v16 = MALLOC(*((unsigned int *)a2 + 7));
      this[4].OwningThread = v16;
      v9 = v16;
      if ( !v16 )
      {
        v10 = 8;
        v2 = 8;
        if ( (Microsoft_Windows_Network_Connection_BrokerEnableBits & 1) != 0 )
        {
          v11 = L"SharedSocket:ImportSslContext Allocating PlainBuffer is failing";
          goto LABEL_28;
        }
        return v2;
      }
      v17 = *((_DWORD *)a2 + 7);
      HIDWORD(this[4].DebugInfo) = v17;
      memcpy_0(v9, *((const void **)a2 + 5), v17);
    }
    v12 = (*((__int64 (__fastcall **)(HANDLE, _OWORD *, _QWORD, HANDLE *))this[5].OwningThread + 21))(
            this[3].OwningThread,
            v19,
            0,
            &this[3].LockSemaphore);
    v2 = v12;
    if ( !v12 || (Microsoft_Windows_Network_Connection_BrokerEnableBits & 1) == 0 )
      return v2;
    v11 = L"SharedSocket:ImportSecurityContext failed";
LABEL_27:
    v10 = v12;
    goto LABEL_28;
  }
  v14 = MALLOC(*((unsigned int *)a2 + 6));
  *(_QWORD *)&this[4].LockCount = v14;
  v9 = v14;
  if ( v14 )
  {
    v15 = *((_DWORD *)a2 + 6);
    LODWORD(this[4].DebugInfo) = v15;
    memcpy_0(v9, *((const void **)a2 + 4), v15);
    goto LABEL_18;
  }
  v10 = 8;
  v2 = 8;
  if ( (Microsoft_Windows_Network_Connection_BrokerEnableBits & 1) != 0 )
  {
    v11 = L"SharedSocket:ImportSslContext Allocating CipherData is failing";
    goto LABEL_28;
  }
  return v2;
}

```

## disassembly

```asm
0x180027fec  push    rbx
0x180027fee  push    rbp
0x180027fef  push    rsi
0x180027ff0  push    rdi
0x180027ff1  push    r14
0x180027ff3  sub     rsp, 40h
0x180027ff7  xor     ebx, ebx
0x180027ff9  xorps   xmm0, xmm0
0x180027ffc  mov     rdi, rdx
0x180027fff  mov     rsi, rcx
0x180028002  movups  [rsp+68h+var_38], xmm0
0x180028007  test    rdx, rdx
0x18002800a  jz      loc_1800281BA
0x180028010  add     rcx, 28h ; '('; lpCriticalSection
0x180028014  call    cs:__imp_EnterCriticalSection
0x18002801a  cmp     [rsi+0D8h], rbx
0x180028021  jnz     short loc_180028052
0x180028023  call    cs:__imp_InitSecurityInterfaceW
0x180028029  mov     [rsi+0D8h], rax
0x180028030  test    rax, rax
0x180028033  jnz     short loc_180028052
0x180028035  test    byte ptr cs:Microsoft_Windows_Network_Connection_BrokerEnableBits, 1
0x18002803c  mov     ebx, 139Fh
0x180028041  jz      short loc_180028052
0x180028043  mov     r9d, ebx
0x180028046  lea     r8, aSharedsocketIn_0; "SharedSocket: InitSecurityInterfaceW fa"...
0x18002804d  call    McTemplateU0zq_EventWriteTransfer
0x180028052  lea     rcx, [rsi+28h]; lpCriticalSection
0x180028056  call    cs:__imp_LeaveCriticalSection
0x18002805c  test    ebx, ebx
0x18002805e  jz      short loc_18002807C
0x180028060  test    byte ptr cs:Microsoft_Windows_Network_Connection_BrokerEnableBits, 1
0x180028067  jz      loc_1800281BA
0x18002806d  mov     r9d, ebx
0x180028070  lea     r8, aSharedsocketIn; "SharedSocket:InitializeSecurityFunction"...
0x180028077  jmp     loc_1800281B5
0x18002807c  mov     rcx, rsi; this
0x18002807f  call    ?FreeSslContext@SharedSocket@@AEAAXXZ; SharedSocket::FreeSslContext(void)
0x180028084  mov     rcx, [rdi]
0x180028087  lea     r14, [rsi+88h]
0x18002808e  mov     rdx, r14
0x180028091  call    NcbUtilsAllocCopyString
0x180028096  mov     ebx, eax
0x180028098  test    eax, eax
0x18002809a  jz      short loc_1800280B5
0x18002809c  test    byte ptr cs:Microsoft_Windows_Network_Connection_BrokerEnableBits, 1
0x1800280a3  jz      loc_1800281BA
0x1800280a9  lea     r8, aSharedsocketIm_1; "SharedSocket:ImportSslContext copy stri"...
0x1800280b0  jmp     loc_1800281B2
0x1800280b5  cmp     qword ptr [rdi+20h], 0
0x1800280ba  mov     eax, [rdi+8]
0x1800280bd  mov     dword ptr [rsp+68h+var_38], eax
0x1800280c1  mov     eax, [rdi+0Ch]
0x1800280c4  mov     dword ptr [rsp+68h+var_38+4], eax
0x1800280c8  mov     rax, [rdi+10h]
0x1800280cc  mov     qword ptr [rsp+68h+var_38+8], rax
0x1800280d1  jz      short loc_180028125
0x1800280d3  cmp     dword ptr [rdi+18h], 0
0x1800280d7  jz      short loc_180028125
0x1800280d9  mov     ecx, [rdi+18h]; dwBytes
0x1800280dc  call    ?MALLOC@@YAPEAX_K@Z; MALLOC(unsigned __int64)
0x1800280e1  mov     [rsi+0A8h], rax
0x1800280e8  mov     rcx, rax; void *
0x1800280eb  test    rax, rax
0x1800280ee  jnz     short loc_180028110
0x1800280f0  test    byte ptr cs:Microsoft_Windows_Network_Connection_BrokerEnableBits, 1
0x1800280f7  lea     r9d, [rax+8]
0x1800280fb  mov     ebx, r9d
0x1800280fe  jz      loc_1800281BA
0x180028104  lea     r8, aSharedsocketIm_3; "SharedSocket:ImportSslContext Allocatin"...
0x18002810b  jmp     loc_1800281B5
0x180028110  mov     eax, [rdi+18h]
0x180028113  mov     [rsi+0A0h], eax
0x180028119  mov     r8d, eax; Size
0x18002811c  mov     rdx, [rdi+20h]; Src
0x180028120  call    memcpy_0
0x180028125  cmp     qword ptr [rdi+28h], 0
0x18002812a  jz      short loc_180028177
0x18002812c  cmp     dword ptr [rdi+1Ch], 0
0x180028130  jz      short loc_180028177
0x180028132  mov     ecx, [rdi+1Ch]; dwBytes
0x180028135  call    ?MALLOC@@YAPEAX_K@Z; MALLOC(unsigned __int64)
0x18002813a  mov     [rsi+0B0h], rax
0x180028141  mov     rcx, rax; void *
0x180028144  test    rax, rax
0x180028147  jnz     short loc_180028162
0x180028149  test    byte ptr cs:Microsoft_Windows_Network_Connection_BrokerEnableBits, 1
0x180028150  lea     r9d, [rax+8]
0x180028154  mov     ebx, r9d
0x180028157  jz      short loc_1800281BA
0x180028159  lea     r8, aSharedsocketIm_0; "SharedSocket:ImportSslContext Allocatin"...
0x180028160  jmp     short loc_1800281B5
0x180028162  mov     eax, [rdi+1Ch]
0x180028165  mov     [rsi+0A4h], eax
0x18002816b  mov     r8d, eax; Size
0x18002816e  mov     rdx, [rdi+28h]; Src
0x180028172  call    memcpy_0
0x180028177  mov     rax, [rsi+0D8h]
0x18002817e  lea     r9, [rsi+90h]
0x180028185  mov     rcx, [r14]
0x180028188  lea     rdx, [rsp+68h+var_38]
0x18002818d  xor     r8d, r8d
0x180028190  mov     rax, [rax+0A8h]
0x180028197  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002819c  mov     ebx, eax
0x18002819e  test    eax, eax
0x1800281a0  jz      short loc_1800281BA
0x1800281a2  test    byte ptr cs:Microsoft_Windows_Network_Connection_BrokerEnableBits, 1
0x1800281a9  jz      short loc_1800281BA
0x1800281ab  lea     r8, aSharedsocketIm_4; "SharedSocket:ImportSecurityContext fail"...
0x1800281b2  mov     r9d, eax
0x1800281b5  call    McTemplateU0zq_EventWriteTransfer
0x1800281ba  mov     eax, ebx
0x1800281bc  add     rsp, 40h
0x1800281c0  pop     r14
0x1800281c2  pop     rdi
0x1800281c3  pop     rsi
0x1800281c4  pop     rbp
0x1800281c5  pop     rbx
0x1800281c6  retn
```
