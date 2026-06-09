# ARI::ProcessToken::SysAppId::Open(void *,_TOKEN_SECURITY_ATTRIBUTES_INFORMATION * *,_TOKEN_SECURITY_ATTRIBUTE_V1 const * *,bool *)

- ea: `0x1400565e0`
- end: `0x14005677b`
- name: `?Open@SysAppId@ProcessToken@ARI@@YAJPEAXPEAPEAU_TOKEN_SECURITY_ATTRIBUTES_INFORMATION@@PEAPEBU_TOKEN_SECURITY_ATTRIBUTE_V1@@PEA_N@Z`
- size: `411`
- prototype: `__int64 __fastcall(HANDLE TokenHandle, void *, struct _TOKEN_SECURITY_ATTRIBUTES_INFORMATION **, const struct _TOKEN_SECURITY_ATTRIBUTE_V1 **, bool *)`
- caller_count: `1`
- callee_count: `3`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x1400561c4`

## callees

- `0x1400030a8`
- `0x140055b7c`
- `0x1400565e0`

## import_xrefs

- `ntdll!RtlAllocateHeap` at `0x140056679`
- `ntdll!RtlAllocateHeap` at `0x140056679`
- `ntdll!RtlNtStatusToDosErrorNoTeb` at `0x14005663d`
- `ntdll!RtlNtStatusToDosErrorNoTeb` at `0x1400566c6`
- `ntdll!RtlNtStatusToDosErrorNoTeb` at `0x14005663d`
- `ntdll!RtlNtStatusToDosErrorNoTeb` at `0x1400566c6`
- `ntdll!RtlCompareUnicodeString` at `0x140056725`
- `ntdll!RtlCompareUnicodeString` at `0x140056725`
- `ntdll!NtQueryInformationToken` at `0x140056620`
- `ntdll!NtQueryInformationToken` at `0x1400566ba`
- `ntdll!NtQueryInformationToken` at `0x140056620`
- `ntdll!NtQueryInformationToken` at `0x1400566ba`
- `ntdll!RtlInitUnicodeString` at `0x1400566fa`
- `ntdll!RtlInitUnicodeString` at `0x1400566fa`

## pseudocode

```c
ULONG __fastcall ARI::ProcessToken::SysAppId::Open(
        HANDLE TokenHandle,
        _QWORD *a2,
        const UNICODE_STRING **a3,
        const struct _TOKEN_SECURITY_ATTRIBUTE_V1 **a4)
{
  NTSTATUS v7; // eax
  PVOID Heap; // rax
  _DWORD *v10; // rdi
  int v11; // eax
  ULONG v12; // ebx
  _DWORD *v13; // rsi
  __int64 v14; // rbx
  const UNICODE_STRING *v15; // rbp
  struct _UNICODE_STRING DestinationString; // [rsp+30h] [rbp-48h] BYREF
  __int128 v17; // [rsp+40h] [rbp-38h]
  ULONG Size; // [rsp+98h] [rbp+20h] BYREF
  int Size_4; // [rsp+9Ch] [rbp+24h]

  Size_4 = HIDWORD(a4);
  Size = 0;
  v7 = NtQueryInformationToken(TokenHandle, TokenSecurityAttributes, 0, 0, &Size);
  if ( v7 == -1073741789 )
  {
    *(_QWORD *)&DestinationString.Length = 0;
    if ( is_mul_ok(Size, 0x10u)
      && (Heap = RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, (Size * (unsigned __int128)0x10uLL) >> 64, 16LL * Size),
          (v10 = Heap) != 0) )
    {
      memset_0(Heap, 0, Size);
      v11 = NtQueryInformationToken(TokenHandle, TokenSecurityAttributes, v10, Size, &Size);
      if ( v11 >= 0 )
      {
        v13 = v10 + 1;
        if ( v10[1]
          && (DestinationString = 0, RtlInitUnicodeString(&DestinationString, L"WIN://SYSAPPID"), v14 = 0, v17 = 0, *v13) )
        {
          while ( 1 )
          {
            v15 = (const UNICODE_STRING *)(*((_QWORD *)v10 + 1) + 40 * v14);
            if ( !RtlCompareUnicodeString(&DestinationString, v15, 1u) )
              break;
            v14 = (unsigned int)(v14 + 1);
            if ( (unsigned int)v14 >= *v13 )
              goto LABEL_13;
          }
          *a3 = v15;
          *a2 = v10;
          ARI::AutoPtrAriHeapDeallocate<_TOKEN_SECURITY_ATTRIBUTES_INFORMATION>(0);
          return 0;
        }
        else
        {
LABEL_13:
          ARI::AutoPtrAriHeapDeallocate<_TOKEN_SECURITY_ATTRIBUTES_INFORMATION>(v10);
          return 1168;
        }
      }
      else
      {
        v12 = RtlNtStatusToDosErrorNoTeb(v11);
        ARI::AutoPtrAriHeapDeallocate<_TOKEN_SECURITY_ATTRIBUTES_INFORMATION>(v10);
        return v12;
      }
    }
    else
    {
      ARI::AutoPtrAriHeapDeallocate<_TOKEN_SECURITY_ATTRIBUTES_INFORMATION>(0);
      return 8;
    }
  }
  else if ( v7 )
  {
    return RtlNtStatusToDosErrorNoTeb(v7);
  }
  else
  {
    return 1359;
  }
}

```

## disassembly

```asm
0x1400565e0  mov     rax, rsp
0x1400565e3  mov     [rax+8], rbx
0x1400565e7  mov     [rax+10h], rbp
0x1400565eb  mov     [rax+20h], r9
0x1400565ef  push    rsi
0x1400565f0  push    rdi
0x1400565f1  push    r12
0x1400565f3  push    r14
0x1400565f5  push    r15
0x1400565f7  sub     rsp, 50h
0x1400565fb  xor     r9d, r9d; TokenInformationLength
0x1400565fe  mov     dword ptr [rax+20h], 0
0x140056605  mov     r15, r8
0x140056608  lea     rax, [rax+20h]
0x14005660c  mov     r12, rdx
0x14005660f  mov     [rsp+78h+ReturnLength], rax; ReturnLength
0x140056614  xor     r8d, r8d; TokenInformation
0x140056617  mov     rbx, rcx
0x14005661a  lea     esi, [r9+27h]
0x14005661e  mov     edx, esi; TokenInformationClass
0x140056620  call    cs:__imp_NtQueryInformationToken
0x140056626  cmp     eax, 0C0000023h
0x14005662b  jz      short loc_140056648
0x14005662d  test    eax, eax
0x14005662f  jnz     short loc_14005663B
0x140056631  mov     eax, 54Fh
0x140056636  jmp     loc_140056762
0x14005663b  mov     ecx, eax; Status
0x14005663d  call    cs:__imp_RtlNtStatusToDosErrorNoTeb
0x140056643  jmp     loc_140056762
0x140056648  mov     ecx, dword ptr [rsp+78h+Size]
0x14005664f  mov     eax, 10h
0x140056654  mul     rcx
0x140056657  mov     qword ptr [rsp+78h+DestinationString.Length], 0
0x140056660  test    rdx, rdx
0x140056663  jnz     loc_140056756
0x140056669  mov     rcx, gs:60h
0x140056672  mov     r8, rax; Size
0x140056675  mov     rcx, [rcx+30h]; HeapHandle
0x140056679  call    cs:__imp_RtlAllocateHeap
0x14005667f  mov     rdi, rax
0x140056682  test    rax, rax
0x140056685  jz      loc_140056756
0x14005668b  mov     r8d, dword ptr [rsp+78h+Size]; Size
0x140056693  xor     edx, edx; Val
0x140056695  mov     rcx, rax; void *
0x140056698  call    memset_0
0x14005669d  mov     r9d, dword ptr [rsp+78h+Size]; TokenInformationLength
0x1400566a5  lea     rax, [rsp+78h+Size]
0x1400566ad  mov     r8, rdi; TokenInformation
0x1400566b0  mov     [rsp+78h+ReturnLength], rax; ReturnLength
0x1400566b5  mov     edx, esi; TokenInformationClass
0x1400566b7  mov     rcx, rbx; TokenHandle
0x1400566ba  call    cs:__imp_NtQueryInformationToken
0x1400566c0  test    eax, eax
0x1400566c2  jns     short loc_1400566DD
0x1400566c4  mov     ecx, eax; Status
0x1400566c6  call    cs:__imp_RtlNtStatusToDosErrorNoTeb
0x1400566cc  mov     rcx, rdi; P
0x1400566cf  mov     ebx, eax
0x1400566d1  call    ??$AutoPtrAriHeapDeallocate@U_TOKEN_SECURITY_ATTRIBUTES_INFORMATION@@@ARI@@YAXPEAU_TOKEN_SECURITY_ATTRIBUTES_INFORMATION@@@Z; ARI::AutoPtrAriHeapDeallocate<_TOKEN_SECURITY_ATTRIBUTES_INFORMATION>(_TOKEN_SECURITY_ATTRIBUTES_INFORMATION *)
0x1400566d6  mov     eax, ebx
0x1400566d8  jmp     loc_140056762
0x1400566dd  lea     rsi, [rdi+4]
0x1400566e1  cmp     dword ptr [rsi], 0
0x1400566e4  jbe     short loc_140056735
0x1400566e6  xorps   xmm0, xmm0
0x1400566e9  lea     rdx, aWinSysappid; "WIN://SYSAPPID"
0x1400566f0  lea     rcx, [rsp+78h+DestinationString]; DestinationString
0x1400566f5  movups  xmmword ptr [rsp+78h+DestinationString.Length], xmm0
0x1400566fa  call    cs:__imp_RtlInitUnicodeString
0x140056700  xor     ebx, ebx
0x140056702  xorps   xmm0, xmm0
0x140056705  movups  [rsp+78h+var_38], xmm0
0x14005670a  cmp     [rsi], ebx
0x14005670c  jbe     short loc_140056735
0x14005670e  mov     rax, [rdi+8]
0x140056712  lea     rcx, [rbx+rbx*4]
0x140056716  mov     r8b, 1; CaseInsensitive
0x140056719  lea     rbp, [rax+rcx*8]
0x14005671d  mov     rdx, rbp; String2
0x140056720  lea     rcx, [rsp+78h+DestinationString]; String1
0x140056725  call    cs:__imp_RtlCompareUnicodeString
0x14005672b  test    eax, eax
0x14005672d  jz      short loc_140056744
0x14005672f  inc     ebx
0x140056731  cmp     ebx, [rsi]
0x140056733  jb      short loc_14005670E
0x140056735  mov     rcx, rdi; P
0x140056738  call    ??$AutoPtrAriHeapDeallocate@U_TOKEN_SECURITY_ATTRIBUTES_INFORMATION@@@ARI@@YAXPEAU_TOKEN_SECURITY_ATTRIBUTES_INFORMATION@@@Z; ARI::AutoPtrAriHeapDeallocate<_TOKEN_SECURITY_ATTRIBUTES_INFORMATION>(_TOKEN_SECURITY_ATTRIBUTES_INFORMATION *)
0x14005673d  mov     eax, 490h
0x140056742  jmp     short loc_140056762
0x140056744  mov     [r15], rbp
0x140056747  xor     ecx, ecx; P
0x140056749  mov     [r12], rdi
0x14005674d  call    ??$AutoPtrAriHeapDeallocate@U_TOKEN_SECURITY_ATTRIBUTES_INFORMATION@@@ARI@@YAXPEAU_TOKEN_SECURITY_ATTRIBUTES_INFORMATION@@@Z; ARI::AutoPtrAriHeapDeallocate<_TOKEN_SECURITY_ATTRIBUTES_INFORMATION>(_TOKEN_SECURITY_ATTRIBUTES_INFORMATION *)
0x140056752  xor     eax, eax
0x140056754  jmp     short loc_140056762
0x140056756  xor     ecx, ecx; P
0x140056758  call    ??$AutoPtrAriHeapDeallocate@U_TOKEN_SECURITY_ATTRIBUTES_INFORMATION@@@ARI@@YAXPEAU_TOKEN_SECURITY_ATTRIBUTES_INFORMATION@@@Z; ARI::AutoPtrAriHeapDeallocate<_TOKEN_SECURITY_ATTRIBUTES_INFORMATION>(_TOKEN_SECURITY_ATTRIBUTES_INFORMATION *)
0x14005675d  mov     eax, 8
0x140056762  lea     r11, [rsp+78h+var_28]
0x140056767  mov     rbx, [r11+30h]
0x14005676b  mov     rbp, [r11+38h]
0x14005676f  mov     rsp, r11
0x140056772  pop     r15
0x140056774  pop     r14
0x140056776  pop     r12
0x140056778  pop     rdi
0x140056779  pop     rsi
0x14005677a  retn
```
