# FwpsAllocateNetBufferAndNetBufferList0

- ea: `0x180004620`
- end: `0x18000488c`
- name: `FwpsAllocateNetBufferAndNetBufferList0`
- size: `620`
- prototype: `NTSTATUS __stdcall(NDIS_HANDLE poolHandle, USHORT contextSize, USHORT contextBackFill, MDL *mdlChain, ULONG dataOffset, SIZE_T dataLength, NET_BUFFER_LIST **netBufferList)`
- caller_count: `0`
- callee_count: `5`
- tags: `authz_impersonation`

## callees

- `0x180004620`
- `0x180004904`
- `0x18000c9b4`
- `0x18000de60`
- `0x1800208c0`

## import_xrefs

- `ntoskrnl!MmBadPointer` at `0x1800046bb`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x180004774`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x180004774`
- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x18000467f`
- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x18000467f`
- `NDIS!NdisFreeNetBufferList` at `0x18000478c`
- `NDIS!NdisFreeNetBufferList` at `0x18000478c`
- `NDIS!NdisAllocateNetBufferAndNetBufferList` at `0x180004660`
- `NDIS!NdisAllocateNetBufferAndNetBufferList` at `0x180004660`
- `NETIO!WfpNblInfoGet` at `0x1800046aa`
- `NETIO!WfpNblInfoGet` at `0x18000472b`
- `NETIO!WfpNblInfoGet` at `0x1800046aa`
- `NETIO!WfpNblInfoGet` at `0x18000472b`
- `NETIO!WfpNblInfoAlloc` at `0x180004715`
- `NETIO!WfpNblInfoAlloc` at `0x180004715`
- `NETIO!WfpNblInfoDestroyIfUnused` at `0x1800047f7`
- `NETIO!WfpNblInfoDestroyIfUnused` at `0x1800047f7`

## string_xrefs

- `0x18000480e`: `ExAllocateFromNPagedLookasideList`
- `0x180004826`: `WfpAllocFromNPagedLookasideList`

## pseudocode

```c
// local variable allocation has failed, the output may be wrong!
NTSTATUS __stdcall FwpsAllocateNetBufferAndNetBufferList0(
        NDIS_HANDLE poolHandle,
        USHORT contextSize,
        USHORT contextBackFill,
        MDL *mdlChain,
        ULONG dataOffset,
        SIZE_T dataLength,
        NET_BUFFER_LIST **netBufferList)
{
  _QWORD *v7; // rdi
  PNET_BUFFER_LIST NetBufferAndNetBufferList; // rsi
  __int64 v9; // rcx
  _QWORD *v10; // rax
  NTSTATUS v11; // ebx
  __int64 v12; // rax
  __int64 v14; // r8
  __int64 v15; // rax
  const char *v16; // rdx
  int v17; // r8d
  __int64 DataOffset; // [rsp+20h] [rbp-18h]

  if ( !netBufferList )
  {
    v11 = -1071513572;
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x1000) != 0 )
    {
      WPP_SF_sd(
        (__int64)WPP_GLOBAL_Control->AttachedDevice,
        0xAu,
        contextBackFill,
        "FwpsAllocateNetBufferAndNetBufferList0",
        -1071513572);
    }
    return v11;
  }
  v7 = 0;
  if ( poolHandle )
  {
    NetBufferAndNetBufferList = NdisAllocateNetBufferAndNetBufferList(
                                  poolHandle,
                                  contextSize,
                                  contextBackFill,
                                  mdlChain,
                                  dataOffset,
                                  dataLength);
    if ( NetBufferAndNetBufferList )
    {
      v7 = ExAllocateFromNPagedLookasideList(&gFwpNblInfo);
      if ( !v7 )
      {
        v15 = WfpReportSysErrorAsNtStatus(v9, (int)"ExAllocateFromNPagedLookasideList", -1073741801);
        v11 = v15;
        if ( v15 )
        {
          WfpReportError(v15, (int)"WfpAllocFromNPagedLookasideList");
LABEL_20:
          NdisFreeNetBufferList(NetBufferAndNetBufferList);
          return v11;
        }
      }
      memset(v7, 0, 0x178u);
      v10 = (_QWORD *)WfpNblInfoGet(NetBufferAndNetBufferList);
      if ( v10 && v10 != MmBadPointer )
        goto LABEL_7;
      v11 = WfpNblInfoAlloc(NetBufferAndNetBufferList);
      if ( !v11 )
      {
        v10 = (_QWORD *)WfpNblInfoGet(NetBufferAndNetBufferList);
LABEL_7:
        if ( v7 )
        {
          *(_DWORD *)v7 = 1852864326;
          v7[1] = v10;
          v10[1] = v7;
        }
        else
        {
          v10[1] = 0;
          WfpNblInfoDestroyIfUnused(NetBufferAndNetBufferList);
        }
        v11 = 0;
        *netBufferList = NetBufferAndNetBufferList;
        _InterlockedIncrement(&dword_180048700);
        return v11;
      }
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x1000) != 0 )
      {
        LODWORD(DataOffset) = v11;
        WPP_SF_sd((__int64)WPP_GLOBAL_Control->AttachedDevice, 0xAu, v14, "WfpNblInfoAlloc", DataOffset);
      }
      WfpReportError(v11, (int)"FwppSetPacketInfo");
      goto LABEL_17;
    }
    v17 = -1073741801;
    v16 = "NdisAllocateNetBufferAndNetBufferList";
  }
  else
  {
    NetBufferAndNetBufferList = 0;
    v16 = "FwpsAllocateNetBufferAndNetBufferList0";
    v17 = -1071513572;
  }
  v12 = WfpReportSysErrorAsNtStatus((__int64)poolHandle, (int)v16, v17);
  v11 = v12;
  if ( !v12 )
    return v11;
LABEL_17:
  if ( v7 )
    ExFreeToNPagedLookasideList(&gFwpNblInfo, v7);
  if ( NetBufferAndNetBufferList )
    goto LABEL_20;
  return v11;
}

```

## disassembly

```asm
0x180004620  mov     [rsp+arg_10], rbx
0x180004625  push    r14
0x180004627  sub     rsp, 30h
0x18000462b  mov     r14, [rsp+38h+netBufferList]
0x180004630  test    r14, r14
0x180004633  jz      loc_18000479D
0x180004639  mov     [rsp+38h+arg_0], rsi
0x18000463e  mov     [rsp+38h+arg_8], rdi
0x180004643  xor     edi, edi
0x180004645  test    rcx, rcx
0x180004648  jz      loc_18000483A
0x18000464e  mov     rax, [rsp+38h+dataLength]
0x180004653  mov     [rsp+38h+DataLength], rax; DataLength
0x180004658  mov     eax, [rsp+38h+dataOffset]
0x18000465c  mov     dword ptr [rsp+38h+DataOffset], eax; DataOffset
0x180004660  call    cs:__imp_NdisAllocateNetBufferAndNetBufferList
0x180004667  nop     dword ptr [rax+rax+00h]
0x18000466c  mov     rsi, rax
0x18000466f  test    rax, rax
0x180004672  jz      loc_18000484F
0x180004678  lea     rcx, gFwpNblInfo; Lookaside
0x18000467f  call    cs:__imp_ExAllocateFromNPagedLookasideList
0x180004686  nop     dword ptr [rax+rax+00h]
0x18000468b  mov     rdi, rax
0x18000468e  test    rax, rax
0x180004691  jz      loc_180004808
0x180004697  xor     edx, edx; Val
0x180004699  mov     r8d, 178h; Size
0x18000469f  mov     rcx, rdi; void *
0x1800046a2  call    memset
0x1800046a7  mov     rcx, rsi
0x1800046aa  call    cs:__imp_WfpNblInfoGet
0x1800046b1  nop     dword ptr [rax+rax+00h]
0x1800046b6  test    rax, rax
0x1800046b9  jz      short loc_180004712
0x1800046bb  mov     rcx, cs:MmBadPointer
0x1800046c2  cmp     rax, [rcx]
0x1800046c5  jz      short loc_180004712
0x1800046c7  test    rdi, rdi
0x1800046ca  jz      loc_1800047F0
0x1800046d0  mov     dword ptr [rdi], 6E707746h
0x1800046d6  mov     [rdi+8], rax
0x1800046da  mov     [rax+8], rdi
0x1800046de  xor     ebx, ebx
0x1800046e0  mov     [r14], rsi
0x1800046e3  lock inc cs:dword_180048700
0x1800046ea  jmp     short loc_1800046F9
0x1800046ec  call    WfpReportSysErrorAsNtStatus
0x1800046f1  mov     rbx, rax
0x1800046f4  test    rax, rax
0x1800046f7  jnz     short loc_180004765
0x1800046f9  mov     rsi, [rsp+38h+arg_0]
0x1800046fe  mov     rdi, [rsp+38h+arg_8]
0x180004703  mov     eax, ebx
0x180004705  mov     rbx, [rsp+38h+arg_10]
0x18000470a  add     rsp, 30h
0x18000470e  pop     r14
0x180004710  retn
0x180004712  mov     rcx, rsi
0x180004715  call    cs:__imp_WfpNblInfoAlloc
0x18000471c  nop     dword ptr [rax+rax+00h]
0x180004721  movsxd  rbx, eax
0x180004724  test    eax, eax
0x180004726  jnz     short loc_180004739
0x180004728  mov     rcx, rsi
0x18000472b  call    cs:__imp_WfpNblInfoGet
0x180004732  nop     dword ptr [rax+rax+00h]
0x180004737  jmp     short loc_1800046C7
0x180004739  mov     rcx, cs:WPP_GLOBAL_Control
0x180004740  lea     rax, WPP_GLOBAL_Control
0x180004747  cmp     rcx, rax
0x18000474a  jz      short loc_180004756
0x18000474c  cmp     byte ptr [rcx+29h], 2
0x180004750  jnb     loc_180004861
0x180004756  lea     rdx, aFwppsetpacketi; "FwppSetPacketInfo"
0x18000475d  mov     rcx, rbx
0x180004760  call    WfpReportError
0x180004765  test    rdi, rdi
0x180004768  jz      short loc_180004780
0x18000476a  mov     rdx, rdi; Entry
0x18000476d  lea     rcx, gFwpNblInfo; Lookaside
0x180004774  call    cs:__imp_ExFreeToNPagedLookasideList
0x18000477b  nop     dword ptr [rax+rax+00h]
0x180004780  test    rsi, rsi
0x180004783  jz      loc_1800046F9
0x180004789  mov     rcx, rsi; NetBufferList
0x18000478c  call    cs:__imp_NdisFreeNetBufferList
0x180004793  nop     dword ptr [rax+rax+00h]
0x180004798  jmp     loc_1800046F9
0x18000479d  mov     rcx, cs:WPP_GLOBAL_Control
0x1800047a4  lea     rax, WPP_GLOBAL_Control
0x1800047ab  mov     rbx, 0FFFFFFFFC022001Ch
0x1800047b2  cmp     rcx, rax
0x1800047b5  jz      loc_180004703
0x1800047bb  cmp     byte ptr [rcx+29h], 2
0x1800047bf  jb      loc_180004703
0x1800047c5  test    dword ptr [rcx+2Ch], 1000h
0x1800047cc  jz      loc_180004703
0x1800047d2  mov     rcx, [rcx+18h]
0x1800047d6  lea     r9, aFwpsallocatene; "FwpsAllocateNetBufferAndNetBufferList0"
0x1800047dd  mov     edx, 0Ah
0x1800047e2  mov     dword ptr [rsp+38h+DataOffset], ebx
0x1800047e6  call    WPP_SF_sd
0x1800047eb  jmp     loc_180004703
0x1800047f0  mov     rcx, rsi
0x1800047f3  mov     [rax+8], rdi
0x1800047f7  call    cs:__imp_WfpNblInfoDestroyIfUnused
0x1800047fe  nop     dword ptr [rax+rax+00h]
0x180004803  jmp     loc_1800046DE
0x180004808  mov     r8d, 0C0000017h
0x18000480e  lea     rdx, aExallocatefrom; "ExAllocateFromNPagedLookasideList"
0x180004815  call    WfpReportSysErrorAsNtStatus
0x18000481a  mov     rbx, rax
0x18000481d  test    rax, rax
0x180004820  jz      loc_180004697
0x180004826  lea     rdx, aWfpallocfromnp; "WfpAllocFromNPagedLookasideList"
0x18000482d  mov     rcx, rax
0x180004830  call    WfpReportError
0x180004835  jmp     loc_180004789
0x18000483a  xor     esi, esi
0x18000483c  lea     rdx, aFwpsallocatene; "FwpsAllocateNetBufferAndNetBufferList0"
0x180004843  mov     r8, 0FFFFFFFFC022001Ch
0x18000484a  jmp     loc_1800046EC
0x18000484f  mov     r8d, 0C0000017h
0x180004855  lea     rdx, aNdisallocatene_1; "NdisAllocateNetBufferAndNetBufferList"
0x18000485c  jmp     loc_1800046EC
0x180004861  test    dword ptr [rcx+2Ch], 1000h
0x180004868  jz      loc_180004756
0x18000486e  mov     rcx, [rcx+18h]
0x180004872  lea     r9, aWfpnblinfoallo; "WfpNblInfoAlloc"
0x180004879  mov     edx, 0Ah
0x18000487e  mov     dword ptr [rsp+38h+DataOffset], ebx
0x180004882  call    WPP_SF_sd
0x180004887  jmp     loc_180004756
```
