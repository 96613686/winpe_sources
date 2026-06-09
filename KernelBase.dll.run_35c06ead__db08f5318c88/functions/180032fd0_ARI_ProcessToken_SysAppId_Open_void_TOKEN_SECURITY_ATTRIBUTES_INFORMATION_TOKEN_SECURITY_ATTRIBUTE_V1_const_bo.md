# ARI::ProcessToken::SysAppId::Open(void *,_TOKEN_SECURITY_ATTRIBUTES_INFORMATION * *,_TOKEN_SECURITY_ATTRIBUTE_V1 const * *,bool *)

- ea: `0x180032fd0`
- end: `0x1800331f3`
- name: `?Open@SysAppId@ProcessToken@ARI@@YAJPEAXPEAPEAU_TOKEN_SECURITY_ATTRIBUTES_INFORMATION@@PEAPEBU_TOKEN_SECURITY_ATTRIBUTE_V1@@PEA_N@Z`
- size: `547`
- prototype: `__int64 __fastcall(HANDLE TokenHandle, void *, struct _TOKEN_SECURITY_ATTRIBUTES_INFORMATION **, const struct _TOKEN_SECURITY_ATTRIBUTE_V1 **, bool *)`
- caller_count: `2`
- callee_count: `3`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x1800282b0`
- `0x1800287a4`

## callees

- `0x180032fd0`
- `0x180033d08`
- `0x18012d119`

## import_xrefs

- `ntdll!RtlInitUnicodeString` at `0x180033123`
- `ntdll!RtlInitUnicodeString` at `0x180033142`
- `ntdll!RtlInitUnicodeString` at `0x180033123`
- `ntdll!RtlInitUnicodeString` at `0x180033142`
- `ntdll!RtlNtStatusToDosErrorNoTeb` at `0x1800331ca`
- `ntdll!RtlNtStatusToDosErrorNoTeb` at `0x18018d78c`
- `ntdll!RtlNtStatusToDosErrorNoTeb` at `0x1800331ca`
- `ntdll!RtlNtStatusToDosErrorNoTeb` at `0x18018d78c`
- `ntdll!NtQueryInformationToken` at `0x180033012`
- `ntdll!NtQueryInformationToken` at `0x1800330de`
- `ntdll!NtQueryInformationToken` at `0x180033012`
- `ntdll!NtQueryInformationToken` at `0x1800330de`
- `ntdll!RtlCompareUnicodeString` at `0x180033171`
- `ntdll!RtlCompareUnicodeString` at `0x18003318b`
- `ntdll!RtlCompareUnicodeString` at `0x180033171`
- `ntdll!RtlCompareUnicodeString` at `0x18003318b`
- `ntdll!RtlFreeHeap` at `0x18003305d`
- `ntdll!RtlFreeHeap` at `0x18003305d`
- `ntdll!RtlAllocateHeap` at `0x18003309e`
- `ntdll!RtlAllocateHeap` at `0x18003309e`

## pseudocode

```c
ULONG __fastcall ARI::ProcessToken::SysAppId::Open(
        HANDLE TokenHandle,
        _QWORD *a2,
        struct _TOKEN_SECURITY_ATTRIBUTES_INFORMATION **a3,
        const struct _TOKEN_SECURITY_ATTRIBUTE_V1 **a4)
{
  NTSTATUS v8; // eax
  PVOID Heap; // rax
  PVOID v11; // rbx
  int v12; // eax
  char v13; // r15
  bool v14; // r14
  unsigned int v15; // edi
  __int64 v16; // rax
  struct _TOKEN_SECURITY_ATTRIBUTES_INFORMATION *v17; // rbp
  ULONG v18; // edi
  struct _UNICODE_STRING DestinationString; // [rsp+30h] [rbp-48h] BYREF
  UNICODE_STRING String1; // [rsp+40h] [rbp-38h] BYREF
  ULONG TokenInformationLength; // [rsp+98h] [rbp+20h] BYREF

  if ( a4 )
    *(_BYTE *)a4 = 0;
  TokenInformationLength = 0;
  v8 = NtQueryInformationToken(TokenHandle, TokenSecurityAttributes, 0, 0, &TokenInformationLength);
  if ( v8 == -1073741789 )
  {
    *(_QWORD *)&DestinationString.Length = 0;
    if ( is_mul_ok(TokenInformationLength, 0x10u)
      && (Heap = RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 0, 16LL * TokenInformationLength), (v11 = Heap) != 0) )
    {
      memset_0(Heap, 0, TokenInformationLength);
      v12 = NtQueryInformationToken(
              TokenHandle,
              TokenSecurityAttributes,
              v11,
              TokenInformationLength,
              &TokenInformationLength);
      if ( v12 < 0 )
      {
        v18 = RtlNtStatusToDosErrorNoTeb(v12);
        AutoPtrRtlHeapDeallocate<tag_STATE_ENUM_ITEM>(v11);
        return v18;
      }
      else
      {
        if ( *((_DWORD *)v11 + 1) )
        {
          v13 = 1;
          v14 = a4 != 0;
          DestinationString = 0;
          RtlInitUnicodeString(&DestinationString, L"WIN://SYSAPPID");
          String1 = 0;
          if ( a4 )
            RtlInitUnicodeString(&String1, L"WIN://PKG");
          v15 = 0;
          while ( v15 < *((_DWORD *)v11 + 1) )
          {
            v16 = *((_QWORD *)v11 + 1);
            v17 = (struct _TOKEN_SECURITY_ATTRIBUTES_INFORMATION *)(v16 + 40LL * v15);
            if ( v13 && !RtlCompareUnicodeString(&DestinationString, (PCUNICODE_STRING)(v16 + 40LL * v15), 1u) )
            {
              *a3 = v17;
              if ( !v14 )
                goto LABEL_23;
              v13 = 0;
              ++v15;
            }
            else
            {
              if ( v14 && !RtlCompareUnicodeString(&String1, (PCUNICODE_STRING)v17, 1u) )
              {
                *(_BYTE *)a4 = 1;
                if ( !v13 )
                {
LABEL_23:
                  *a2 = v11;
                  AutoPtrRtlHeapDeallocate<tag_STATE_ENUM_ITEM>(0);
                  return 0;
                }
                v14 = 0;
              }
              ++v15;
            }
          }
        }
        RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v11);
        return 1168;
      }
    }
    else
    {
      return 8;
    }
  }
  else if ( v8 )
  {
    return RtlNtStatusToDosErrorNoTeb(v8);
  }
  else
  {
    return 1359;
  }
}

```

## disassembly

```asm
0x180032fd0  push    rbp
0x180032fd2  push    rsi
0x180032fd3  push    rdi
0x180032fd4  push    r12
0x180032fd6  push    r13
0x180032fd8  sub     rsp, 50h
0x180032fdc  mov     rsi, r9
0x180032fdf  mov     r12, r8
0x180032fe2  mov     r13, rdx
0x180032fe5  mov     rdi, rcx
0x180032fe8  test    r9, r9
0x180032feb  jz      short loc_180032FF1
0x180032fed  mov     byte ptr [r9], 0
0x180032ff1  lea     rax, [rsp+78h+TokenInformationLength]
0x180032ff9  xor     ebp, ebp
0x180032ffb  xor     r9d, r9d; TokenInformationLength
0x180032ffe  mov     [rsp+78h+TokenInformationLength], ebp
0x180033005  xor     r8d, r8d; TokenInformation
0x180033008  mov     [rsp+78h+ReturnLength], rax; ReturnLength
0x18003300d  mov     edx, 27h ; '''; TokenInformationClass
0x180033012  call    cs:__imp_NtQueryInformationToken
0x180033018  cmp     eax, 0C0000023h
0x18003301d  jnz     loc_1800331E1
0x180033023  mov     ecx, [rsp+78h+TokenInformationLength]
0x18003302a  mov     eax, 10h
0x18003302f  mul     rcx
0x180033032  mov     [rsp+78h+arg_0], rbx
0x18003303a  mov     qword ptr [rsp+78h+DestinationString.Length], rbp
0x18003303f  test    rdx, rdx
0x180033042  jz      short loc_18003308C
0x180033044  mov     eax, 8
0x180033049  jmp     short loc_180033078
0x18003304b  mov     rcx, gs:60h
0x180033054  mov     r8, rbx; P
0x180033057  xor     edx, edx; Flags
0x180033059  mov     rcx, [rcx+30h]; HeapHandle
0x18003305d  call    cs:__imp_RtlFreeHeap
0x180033063  mov     eax, 490h
0x180033068  mov     r14, [rsp+78h+arg_8]
0x180033070  mov     r15, [rsp+78h+arg_10]
0x180033078  mov     rbx, [rsp+78h+arg_0]
0x180033080  add     rsp, 50h
0x180033084  pop     r13
0x180033086  pop     r12
0x180033088  pop     rdi
0x180033089  pop     rsi
0x18003308a  pop     rbp
0x18003308b  retn
0x18003308c  mov     rcx, gs:60h
0x180033095  mov     r8, rax; Size
0x180033098  xor     edx, edx; Flags
0x18003309a  mov     rcx, [rcx+30h]; HeapHandle
0x18003309e  call    cs:__imp_RtlAllocateHeap
0x1800330a4  mov     rbx, rax
0x1800330a7  test    rax, rax
0x1800330aa  jz      short loc_180033044
0x1800330ac  mov     r8d, [rsp+78h+TokenInformationLength]; Size
0x1800330b4  xor     edx, edx; Val
0x1800330b6  mov     rcx, rax; void *
0x1800330b9  call    memset_0
0x1800330be  mov     r9d, [rsp+78h+TokenInformationLength]; TokenInformationLength
0x1800330c6  lea     rax, [rsp+78h+TokenInformationLength]
0x1800330ce  mov     r8, rbx; TokenInformation
0x1800330d1  mov     [rsp+78h+ReturnLength], rax; ReturnLength
0x1800330d6  mov     edx, 27h ; '''; TokenInformationClass
0x1800330db  mov     rcx, rdi; TokenHandle
0x1800330de  call    cs:__imp_NtQueryInformationToken
0x1800330e4  test    eax, eax
0x1800330e6  js      loc_1800331C8
0x1800330ec  mov     [rsp+78h+arg_8], r14
0x1800330f4  mov     [rsp+78h+arg_10], r15
0x1800330fc  cmp     [rbx+4], ebp
0x1800330ff  jbe     loc_18003304B
0x180033105  xorps   xmm0, xmm0
0x180033108  lea     rdx, aWinSysappid; "WIN://SYSAPPID"
0x18003310f  test    rsi, rsi
0x180033112  lea     rcx, [rsp+78h+DestinationString]; DestinationString
0x180033117  mov     r15b, 1
0x18003311a  setnz   r14b
0x18003311e  movups  xmmword ptr [rsp+78h+DestinationString.Length], xmm0
0x180033123  call    cs:__imp_RtlInitUnicodeString
0x180033129  xorps   xmm0, xmm0
0x18003312c  movups  xmmword ptr [rsp+78h+String1.Length], xmm0
0x180033131  test    rsi, rsi
0x180033134  jz      short loc_180033148
0x180033136  lea     rdx, aWinPkg; "WIN://PKG"
0x18003313d  lea     rcx, [rsp+78h+String1]; DestinationString
0x180033142  call    cs:__imp_RtlInitUnicodeString
0x180033148  mov     edi, ebp
0x18003314a  cmp     edi, [rbx+4]
0x18003314d  jnb     loc_18003304B
0x180033153  mov     eax, edi
0x180033155  lea     rcx, [rax+rax*4]
0x180033159  mov     rax, [rbx+8]
0x18003315d  lea     rbp, [rax+rcx*8]
0x180033161  test    r15b, r15b
0x180033164  jz      short loc_18003317B
0x180033166  mov     r8b, 1; CaseInsensitive
0x180033169  lea     rcx, [rsp+78h+DestinationString]; String1
0x18003316e  mov     rdx, rbp; String2
0x180033171  call    cs:__imp_RtlCompareUnicodeString
0x180033177  test    eax, eax
0x180033179  jz      short loc_180033199
0x18003317b  test    r14b, r14b
0x18003317e  jz      short loc_180033195
0x180033180  mov     r8b, 1; CaseInsensitive
0x180033183  lea     rcx, [rsp+78h+String1]; String1
0x180033188  mov     rdx, rbp; String2
0x18003318b  call    cs:__imp_RtlCompareUnicodeString
0x180033191  test    eax, eax
0x180033193  jz      short loc_1800331A9
0x180033195  inc     edi
0x180033197  jmp     short loc_18003314A
0x180033199  mov     [r12], rbp
0x18003319d  test    r14b, r14b
0x1800331a0  jz      short loc_1800331B1
0x1800331a2  xor     r15b, r15b
0x1800331a5  inc     edi
0x1800331a7  jmp     short loc_18003314A
0x1800331a9  mov     byte ptr [rsi], 1
0x1800331ac  test    r15b, r15b
0x1800331af  jnz     short loc_1800331C3
0x1800331b1  xor     ecx, ecx; P
0x1800331b3  mov     [r13+0], rbx
0x1800331b7  call    ??$AutoPtrRtlHeapDeallocate@Utag_STATE_ENUM_ITEM@@@@YAXPEAUtag_STATE_ENUM_ITEM@@@Z; AutoPtrRtlHeapDeallocate<tag_STATE_ENUM_ITEM>(tag_STATE_ENUM_ITEM *)
0x1800331bc  xor     eax, eax
0x1800331be  jmp     loc_180033068
0x1800331c3  xor     r14b, r14b
0x1800331c6  jmp     short loc_180033195
0x1800331c8  mov     ecx, eax; Status
0x1800331ca  call    cs:__imp_RtlNtStatusToDosErrorNoTeb
0x1800331d0  mov     rcx, rbx; P
0x1800331d3  mov     edi, eax
0x1800331d5  call    ??$AutoPtrRtlHeapDeallocate@Utag_STATE_ENUM_ITEM@@@@YAXPEAUtag_STATE_ENUM_ITEM@@@Z; AutoPtrRtlHeapDeallocate<tag_STATE_ENUM_ITEM>(tag_STATE_ENUM_ITEM *)
0x1800331da  mov     eax, edi
0x1800331dc  jmp     loc_180033078
0x1800331e1  test    eax, eax
0x1800331e3  jnz     loc_18018D78A
0x1800331e9  mov     eax, 54Fh
0x1800331ee  jmp     loc_180033080
0x18018d78a  mov     ecx, eax; Status
0x18018d78c  call    cs:__imp_RtlNtStatusToDosErrorNoTeb
0x18018d792  nop
0x18018d793  jmp     loc_180033080
```
