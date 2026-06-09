# NetioNcmGetAllNotificationChannelContextParameters

- ea: `0x1400348f0`
- end: `0x140034ac5`
- name: `NetioNcmGetAllNotificationChannelContextParameters`
- size: `469`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x1400348f0`
- `0x140034bb0`
- `0x140038c80`
- `0x1400512d8`

## import_xrefs

- `ntoskrnl!KeLowerIrql` at `0x140034aab`
- `ntoskrnl!KeLowerIrql` at `0x140034aab`
- `ntoskrnl!PsGetCurrentProcessId` at `0x140034976`
- `ntoskrnl!PsGetCurrentProcessId` at `0x140034976`
- `ntoskrnl!RtlGetNextEntryHashTable` at `0x1400349db`
- `ntoskrnl!RtlGetNextEntryHashTable` at `0x1400349db`
- `ntoskrnl!RtlLookupEntryHashTable` at `0x1400349b3`
- `ntoskrnl!RtlLookupEntryHashTable` at `0x1400349b3`

## pseudocode

```c
__int64 __fastcall NetioNcmGetAllNotificationChannelContextParameters(unsigned int *a1, __int64 a2)
{
  __int64 v5; // rdx
  ULONG_PTR v6; // rdx
  PRTL_DYNAMIC_HASH_TABLE_ENTRY i; // rax
  ULONG_PTR j; // rcx
  unsigned int v9; // edi
  ULONG_PTR v10; // rax
  __int64 v11; // rcx
  struct _RTL_DYNAMIC_HASH_TABLE_CONTEXT Context; // [rsp+20h] [rbp-28h] BYREF

  memset(&Context, 0, sizeof(Context));
  if ( NcmGlobal != 1 )
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 3u
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x200000) != 0 )
    {
      WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 44, WPP_b82db9e625ba361a08c79e9c4a088c0e_Traceguids);
    }
    return 3221225506LL;
  }
  *(_OWORD *)a2 = 0;
  *(_QWORD *)(a2 + 16) = 0;
  RtlAcquireReadLock(&SpinLock);
  if ( (unsigned int)PsGetCurrentProcessId() != dword_14009B004 )
  {
    LOBYTE(v5) = 0;
    RtlReleaseReadLock(&SpinLock, v5);
    return 3221225506LL;
  }
  v6 = *a1;
  *(_OWORD *)&Context.ChainHead = 0;
  for ( i = RtlLookupEntryHashTable(&stru_14009B030, v6, &Context);
        i;
        i = RtlGetNextEntryHashTable(&stru_14009B030, &Context) )
  {
    if ( LODWORD(i[1].Linkage.Flink) == *a1 )
    {
      for ( j = i[1].Signature; (ULONG_PTR *)j != &i[1].Signature; j = *(_QWORD *)j )
      {
        if ( *(_QWORD *)(j + 40) == *((_QWORD *)a1 + 1) )
        {
          v9 = 0;
          *(_DWORD *)a2 = *(_DWORD *)(j + 288);
          *(_DWORD *)(a2 + 4) = (*(_DWORD *)(j + 300) >> 4) & 0xF;
          *(_DWORD *)(a2 + 8) = (*(_DWORD *)(j + 300) >> 8) & 0xF;
          *(_DWORD *)(a2 + 12) = *(_WORD *)(j + 302) & 0xF;
          *(_WORD *)(a2 + 16) = *(_WORD *)(j + 292);
          *(_DWORD *)(a2 + 20) = *(_DWORD *)(j + 296);
          v10 = j + 272;
          v11 = *(_QWORD *)(j + 272);
          if ( v11 != v10 )
            *(_BYTE *)(a2 + 18) = *(_BYTE *)(v11 + 80);
          goto LABEL_24;
        }
      }
      break;
    }
  }
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 3u
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x200000) != 0 )
  {
    WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 45, WPP_b82db9e625ba361a08c79e9c4a088c0e_Traceguids);
  }
  v9 = -1073741275;
LABEL_24:
  _InterlockedDecrement(&dword_14009B060);
  KeLowerIrql(0);
  return v9;
}

```

## disassembly

```asm
0x1400348f0  mov     [rsp+arg_0], rbx
0x1400348f5  push    rdi
0x1400348f6  sub     rsp, 40h
0x1400348fa  xor     eax, eax
0x1400348fc  mov     [rsp+48h+NewIrql], 0
0x140034901  cmp     cs:NcmGlobal, 1
0x140034908  xorps   xmm0, xmm0
0x14003490b  mov     rbx, rdx
0x14003490e  mov     [rsp+48h+Context.Signature], rax
0x140034913  mov     rdi, rcx
0x140034916  movups  xmmword ptr [rsp+48h+Context.ChainHead], xmm0
0x14003491b  jz      short loc_14003495E
0x14003491d  mov     rcx, cs:WPP_GLOBAL_Control
0x140034924  lea     rax, WPP_GLOBAL_Control
0x14003492b  cmp     rcx, rax
0x14003492e  jz      short loc_140034954
0x140034930  cmp     byte ptr [rcx+29h], 3
0x140034934  jb      short loc_140034954
0x140034936  test    dword ptr [rcx+2Ch], 200000h
0x14003493d  jz      short loc_140034954
0x14003493f  mov     rcx, [rcx+18h]
0x140034943  lea     r8, WPP_b82db9e625ba361a08c79e9c4a088c0e_Traceguids
0x14003494a  mov     edx, 2Ch ; ','
0x14003494f  call    WPP_SF_
0x140034954  mov     eax, 0C0000022h
0x140034959  jmp     loc_140034AB9
0x14003495e  movups  xmmword ptr [rdx], xmm0
0x140034961  mov     [rdx+10h], rax
0x140034965  lea     rcx, SpinLock; SpinLock
0x14003496c  lea     rdx, [rsp+48h+NewIrql]
0x140034971  call    RtlAcquireReadLock
0x140034976  call    cs:__imp_PsGetCurrentProcessId
0x14003497d  nop     dword ptr [rax+rax+00h]
0x140034982  cmp     eax, cs:dword_14009B004
0x140034988  jz      short loc_14003499C
0x14003498a  mov     dl, [rsp+48h+NewIrql]
0x14003498e  lea     rcx, SpinLock
0x140034995  call    RtlReleaseReadLock
0x14003499a  jmp     short loc_140034954
0x14003499c  mov     edx, [rdi]; Signature
0x14003499e  lea     r8, [rsp+48h+Context]; Context
0x1400349a3  xorps   xmm0, xmm0
0x1400349a6  lea     rcx, stru_14009B030; HashTable
0x1400349ad  movdqu  xmmword ptr [rsp+48h+Context.ChainHead], xmm0
0x1400349b3  call    cs:__imp_RtlLookupEntryHashTable
0x1400349ba  nop     dword ptr [rax+rax+00h]
0x1400349bf  test    rax, rax
0x1400349c2  jz      loc_140034A64
0x1400349c8  mov     ecx, [rdi]
0x1400349ca  cmp     [rax+18h], ecx
0x1400349cd  jz      short loc_1400349E9
0x1400349cf  lea     rdx, [rsp+48h+Context]; Context
0x1400349d4  lea     rcx, stru_14009B030; HashTable
0x1400349db  call    cs:__imp_RtlGetNextEntryHashTable
0x1400349e2  nop     dword ptr [rax+rax+00h]
0x1400349e7  jmp     short loc_1400349BF
0x1400349e9  lea     rdx, [rax+28h]
0x1400349ed  mov     rcx, [rdx]
0x1400349f0  cmp     rcx, rdx
0x1400349f3  jz      short loc_140034A64
0x1400349f5  mov     rax, [rdi+8]
0x1400349f9  cmp     [rcx+28h], rax
0x1400349fd  jz      short loc_140034A04
0x1400349ff  mov     rcx, [rcx]
0x140034a02  jmp     short loc_1400349F0
0x140034a04  mov     eax, [rcx+120h]
0x140034a0a  xor     edi, edi
0x140034a0c  mov     [rbx], eax
0x140034a0e  mov     eax, [rcx+12Ch]
0x140034a14  shr     eax, 4
0x140034a17  and     eax, 0Fh
0x140034a1a  mov     [rbx+4], eax
0x140034a1d  mov     eax, [rcx+12Ch]
0x140034a23  shr     eax, 8
0x140034a26  and     eax, 0Fh
0x140034a29  mov     [rbx+8], eax
0x140034a2c  movzx   eax, word ptr [rcx+12Eh]
0x140034a33  and     eax, 0Fh
0x140034a36  mov     [rbx+0Ch], eax
0x140034a39  movzx   eax, word ptr [rcx+124h]
0x140034a40  mov     [rbx+10h], ax
0x140034a44  mov     eax, [rcx+128h]
0x140034a4a  mov     [rbx+14h], eax
0x140034a4d  lea     rax, [rcx+110h]
0x140034a54  mov     rcx, [rax]
0x140034a57  cmp     rcx, rax
0x140034a5a  jz      short loc_140034AA0
0x140034a5c  mov     al, [rcx+50h]
0x140034a5f  mov     [rbx+12h], al
0x140034a62  jmp     short loc_140034AA0
0x140034a64  mov     rcx, cs:WPP_GLOBAL_Control
0x140034a6b  lea     rax, WPP_GLOBAL_Control
0x140034a72  cmp     rcx, rax
0x140034a75  jz      short loc_140034A9B
0x140034a77  cmp     byte ptr [rcx+29h], 3
0x140034a7b  jb      short loc_140034A9B
0x140034a7d  test    dword ptr [rcx+2Ch], 200000h
0x140034a84  jz      short loc_140034A9B
0x140034a86  mov     rcx, [rcx+18h]
0x140034a8a  lea     r8, WPP_b82db9e625ba361a08c79e9c4a088c0e_Traceguids
0x140034a91  mov     edx, 2Dh ; '-'
0x140034a96  call    WPP_SF_
0x140034a9b  mov     edi, 0C0000225h
0x140034aa0  lock dec cs:dword_14009B060
0x140034aa7  mov     cl, [rsp+48h+NewIrql]; NewIrql
0x140034aab  call    cs:__imp_KeLowerIrql
0x140034ab2  nop     dword ptr [rax+rax+00h]
0x140034ab7  mov     eax, edi
0x140034ab9  mov     rbx, [rsp+48h+arg_0]
0x140034abe  add     rsp, 40h
0x140034ac2  pop     rdi
0x140034ac3  retn
```
