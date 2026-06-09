# AlpcPort::CreateServerPort(_GUID const &,SIPC_SERVICE_BOUNDARY,void *,SipcPort * *)

- ea: `0x180027f1c`
- end: `0x180028171`
- name: `?CreateServerPort@AlpcPort@@SAJAEBU_GUID@@W4SIPC_SERVICE_BOUNDARY@@PEAXPEAPEAVSipcPort@@@Z`
- size: `597`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `file_ops, authz_impersonation, loader_planting, service_task, broker_com_uri`

## callers

- `0x180042b60`

## callees

- `0x18000c11c`
- `0x180024b24`
- `0x180024d58`
- `0x180027f1c`
- `0x180029b8c`
- `0x18004c8e0`

## import_xrefs

- `ntdll!NtAlpcCreatePort` at `0x1800280cd`
- `ntdll!NtAlpcCreatePort` at `0x1800280cd`
- `ntdll!RtlAllocateHeap` at `0x180027f63`
- `ntdll!RtlAllocateHeap` at `0x180027f63`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002806e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002806e`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002809a`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180028106`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180028137`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002809a`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180028106`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180028137`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x18002805e`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x18002805e`

## pseudocode

```c
__int64 __fastcall AlpcPort::CreateServerPort(__int64 a1, __int64 a2, __int64 a3, AlpcPort **a4)
{
  char *Heap; // rax
  AlpcPort *v6; // rbx
  signed int v7; // esi
  signed int LastError; // eax
  int v9; // edi
  int v10; // esi
  int v11; // esi
  PSECURITY_DESCRIPTOR v12; // rcx
  const struct std::nothrow_t *v13; // rdx
  PSECURITY_DESCRIPTOR SecurityDescriptor; // [rsp+20h] [rbp-E0h] BYREF
  __int128 v16; // [rsp+28h] [rbp-D8h] BYREF
  _BYTE *v17; // [rsp+38h] [rbp-C8h]
  __int64 v18; // [rsp+40h] [rbp-C0h]
  PSECURITY_DESCRIPTOR v19; // [rsp+48h] [rbp-B8h]
  const struct _SECURITY_QUALITY_OF_SERVICE *v20; // [rsp+50h] [rbp-B0h]
  _BYTE v21[192]; // [rsp+60h] [rbp-A0h] BYREF

  *a4 = 0;
  Heap = (char *)RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 0, 0x1F8u);
  v6 = (AlpcPort *)Heap;
  if ( !Heap )
    return 2147942414LL;
  *((_QWORD *)Heap + 4) = 0;
  *((_DWORD *)Heap + 10) = 0;
  *((_DWORD *)Heap + 6) = 0;
  Heap[44] = 1;
  *((_QWORD *)Heap + 2) = Heap + 8;
  *((_QWORD *)Heap + 1) = Heap + 8;
  *(_QWORD *)Heap = &AlpcPort::`vftable';
  *((_QWORD *)Heap + 6) = 0;
  *(_OWORD *)(Heap + 56) = 0;
  *(_OWORD *)(Heap + 72) = 0;
  *((_QWORD *)Heap + 11) = 0;
  *((_QWORD *)Heap + 53) = 0;
  *((_WORD *)Heap + 29) = 40;
  *((_DWORD *)Heap + 106) = 1610612736;
  *((_WORD *)Heap + 248) = 0;
  v7 = SipcPort::Initialize((SipcPort *)Heap);
  if ( v7 < 0 )
  {
LABEL_18:
    AlpcPort::~AlpcPort(v6);
    operator delete(v6, v13);
    return (unsigned int)v7;
  }
  AlpcPortString::AlpcPortString(v21, &GameInputServer::c_gameInputServiceGuid, 1);
  v18 = 0;
  v20 = &AlpcPort::c_anonymousSecurityQos;
  v19 = 0;
  v17 = v21;
  v16 = *(_OWORD *)&AlpcPort::c_serverObjectAttributes.Length;
  SecurityDescriptor = 0;
  if ( !ConvertStringSecurityDescriptorToSecurityDescriptorW(
          L"D:(A;;GA;;;WD)(A;;0x001F0001;;;AC)(A;;0x001F0001;;;SY)(A;;0x00020001;;;BA)",
          1u,
          &SecurityDescriptor,
          0) )
  {
    LastError = GetLastError();
    if ( LastError > 0 )
      LastError = (unsigned __int16)LastError | 0x80070000;
    v9 = -2147418113;
    if ( LastError < 0 )
      v9 = LastError;
LABEL_8:
    if ( SecurityDescriptor )
    {
      LocalFree(SecurityDescriptor);
      SecurityDescriptor = 0;
    }
    v7 = v9;
    goto LABEL_18;
  }
  v19 = SecurityDescriptor;
  v10 = NtAlpcCreatePort((char *)v6 + 48, &v16, &AlpcPort::c_serverPortAlpcAttributes);
  if ( v10 < 0 )
  {
    v11 = v10 | 0x10000000;
    v9 = -2147418113;
    if ( v11 < 0 )
      v9 = v11;
    goto LABEL_8;
  }
  v12 = SecurityDescriptor;
  if ( !*((_QWORD *)v6 + 6) )
  {
    v7 = v10 | 0x90000000;
    if ( SecurityDescriptor )
    {
      LocalFree(SecurityDescriptor);
      SecurityDescriptor = 0;
    }
    goto LABEL_18;
  }
  *a4 = v6;
  if ( v12 )
    LocalFree(v12);
  return 0;
}

```

## disassembly

```asm
0x180027f1c  mov     [rsp-8+arg_0], rbx
0x180027f21  mov     [rsp-8+arg_8], rsi
0x180027f26  push    rbp
0x180027f27  push    rdi
0x180027f28  push    r14
0x180027f2a  lea     rbp, [rsp-30h]
0x180027f2f  sub     rsp, 130h
0x180027f36  mov     rax, cs:__security_cookie
0x180027f3d  xor     rax, rsp
0x180027f40  mov     [rbp+40h+var_20], rax
0x180027f44  mov     qword ptr [r9], 0
0x180027f4b  xor     edx, edx; Flags
0x180027f4d  mov     rcx, gs:60h
0x180027f56  mov     r8d, 1F8h; Size
0x180027f5c  mov     r14, r9
0x180027f5f  mov     rcx, [rcx+30h]; HeapHandle
0x180027f63  call    cs:__imp_RtlAllocateHeap
0x180027f6a  nop     dword ptr [rax+rax+00h]
0x180027f6f  mov     rbx, rax
0x180027f72  test    rax, rax
0x180027f75  jz      loc_180028147
0x180027f7b  mov     qword ptr [rax+20h], 0
0x180027f83  lea     rcx, [rax+8]
0x180027f87  mov     dword ptr [rax+28h], 0
0x180027f8e  xorps   xmm0, xmm0
0x180027f91  mov     dword ptr [rcx+10h], 0
0x180027f98  mov     edi, 1
0x180027f9d  mov     [rax+2Ch], dil
0x180027fa1  lea     rax, ??_7AlpcPort@@6B@; const AlpcPort::`vftable'
0x180027fa8  mov     [rcx+8], rcx
0x180027fac  mov     [rcx], rcx
0x180027faf  mov     rcx, rbx; this
0x180027fb2  mov     [rbx], rax
0x180027fb5  xor     eax, eax
0x180027fb7  mov     qword ptr [rbx+30h], 0
0x180027fbf  movups  xmmword ptr [rbx+38h], xmm0
0x180027fc3  movups  xmmword ptr [rbx+48h], xmm0
0x180027fc7  mov     [rbx+58h], rax
0x180027fcb  mov     [rbx+1A8h], rax
0x180027fd2  mov     word ptr [rbx+3Ah], 28h ; '('
0x180027fd8  mov     dword ptr [rbx+1A8h], 60000000h
0x180027fe2  mov     [rbx+1F0h], ax
0x180027fe9  call    ?Initialize@SipcPort@@IEAAJXZ; SipcPort::Initialize(void)
0x180027fee  mov     esi, eax
0x180027ff0  test    eax, eax
0x180027ff2  js      loc_18002811B
0x180027ff8  mov     r8d, edi
0x180027ffb  lea     rdx, ?c_gameInputServiceGuid@GameInputServer@@0U_GUID@@B; _GUID const GameInputServer::c_gameInputServiceGuid
0x180028002  lea     rcx, [rsp+140h+var_E0]
0x180028007  call    ??0AlpcPortString@@QEAA@AEBU_GUID@@W4SIPC_SERVICE_BOUNDARY@@@Z; AlpcPortString::AlpcPortString(_GUID const &,SIPC_SERVICE_BOUNDARY)
0x18002800c  mov     rax, cs:qword_180050990
0x180028013  lea     r8, [rsp+140h+SecurityDescriptor]; SecurityDescriptor
0x180028018  movups  xmm0, cs:?c_serverObjectAttributes@AlpcPort@@0U_OBJECT_ATTRIBUTES@@B; _OBJECT_ATTRIBUTES const AlpcPort::c_serverObjectAttributes
0x18002801f  mov     [rsp+140h+var_100], rax
0x180028024  lea     rcx, ?c_serverDefaultSecurityDescriptor@AlpcPort@@0QBGB; "D:(A;;GA;;;WD)(A;;0x001F0001;;;AC)(A;;0"...
0x18002802b  mov     rax, cs:off_1800509A0
0x180028032  xor     r9d, r9d; SecurityDescriptorSize
0x180028035  mov     [rsp+140h+var_F0], rax
0x18002803a  mov     edx, edi; StringSDRevision
0x18002803c  lea     rax, [rsp+140h+var_E0]
0x180028041  mov     [rsp+140h+var_F8], 0
0x18002804a  mov     [rsp+140h+var_108], rax
0x18002804f  movdqu  [rsp+140h+var_118], xmm0
0x180028055  mov     [rsp+140h+SecurityDescriptor], 0
0x18002805e  call    cs:__imp_ConvertStringSecurityDescriptorToSecurityDescriptorW
0x180028065  nop     dword ptr [rax+rax+00h]
0x18002806a  test    eax, eax
0x18002806c  jnz     short loc_1800280B3
0x18002806e  call    cs:__imp_GetLastError
0x180028075  nop     dword ptr [rax+rax+00h]
0x18002807a  test    eax, eax
0x18002807c  jle     short loc_180028086
0x18002807e  movzx   eax, ax
0x180028081  or      eax, 80070000h
0x180028086  test    eax, eax
0x180028088  mov     edi, 8000FFFFh
0x18002808d  cmovs   edi, eax
0x180028090  mov     rcx, [rsp+140h+SecurityDescriptor]; hMem
0x180028095  test    rcx, rcx
0x180028098  jz      short loc_1800280AF
0x18002809a  call    cs:__imp_LocalFree
0x1800280a1  nop     dword ptr [rax+rax+00h]
0x1800280a6  mov     [rsp+140h+SecurityDescriptor], 0
0x1800280af  mov     esi, edi
0x1800280b1  jmp     short loc_18002811B
0x1800280b3  mov     rax, [rsp+140h+SecurityDescriptor]
0x1800280b8  lea     r8, ?c_serverPortAlpcAttributes@AlpcPort@@0U_ALPC_PORT_ATTRIBUTES@@B; _ALPC_PORT_ATTRIBUTES const AlpcPort::c_serverPortAlpcAttributes
0x1800280bf  lea     rdx, [rsp+140h+var_118]
0x1800280c4  mov     [rsp+140h+var_F8], rax
0x1800280c9  lea     rcx, [rbx+30h]
0x1800280cd  call    cs:__imp_NtAlpcCreatePort
0x1800280d4  nop     dword ptr [rax+rax+00h]
0x1800280d9  mov     esi, eax
0x1800280db  test    eax, eax
0x1800280dd  jns     short loc_1800280EF
0x1800280df  or      esi, 10000000h
0x1800280e5  mov     edi, 8000FFFFh
0x1800280ea  cmovl   edi, esi
0x1800280ed  jmp     short loc_180028090
0x1800280ef  cmp     qword ptr [rbx+30h], 0
0x1800280f4  mov     rcx, [rsp+140h+SecurityDescriptor]; hMem
0x1800280f9  jnz     short loc_18002812F
0x1800280fb  or      esi, 90000000h
0x180028101  test    rcx, rcx
0x180028104  jz      short loc_18002811B
0x180028106  call    cs:__imp_LocalFree
0x18002810d  nop     dword ptr [rax+rax+00h]
0x180028112  mov     [rsp+140h+SecurityDescriptor], 0
0x18002811b  mov     rcx, rbx; this
0x18002811e  call    ??1AlpcPort@@UEAA@XZ; AlpcPort::~AlpcPort(void)
0x180028123  mov     rcx, rbx; P
0x180028126  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18002812b  mov     eax, esi
0x18002812d  jmp     short loc_18002814C
0x18002812f  mov     [r14], rbx
0x180028132  test    rcx, rcx
0x180028135  jz      short loc_180028143
0x180028137  call    cs:__imp_LocalFree
0x18002813e  nop     dword ptr [rax+rax+00h]
0x180028143  xor     eax, eax
0x180028145  jmp     short loc_18002814C
0x180028147  mov     eax, 8007000Eh
0x18002814c  mov     rcx, [rbp+40h+var_20]
0x180028150  xor     rcx, rsp; StackCookie
0x180028153  call    __security_check_cookie
0x180028158  lea     r11, [rsp+140h+var_10]
0x180028160  mov     rbx, [r11+20h]
0x180028164  mov     rsi, [r11+28h]
0x180028168  mov     rsp, r11
0x18002816b  pop     r14
0x18002816d  pop     rdi
0x18002816e  pop     rbp
0x18002816f  retn
```
