# NgcHandler::AllocateAndCopyContainerStringProperty(Microsoft::WRL::ComPtr<INgcCtnrContainer> &,NgcCtnrContainerProperty,std::unique_ptr<ushort,rpcmem_delete<ushort>> *)

- ea: `0x18001e500`
- end: `0x18001e941`
- name: `?AllocateAndCopyContainerStringProperty@NgcHandler@@CAJAEAV?$ComPtr@UINgcCtnrContainer@@@WRL@Microsoft@@W4NgcCtnrContainerProperty@@PEAV?$unique_ptr@GU?$rpcmem_delete@G@@@std@@@Z`
- size: `1089`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x180010654`

## callees

- `0x18001e500`
- `0x18002c640`
- `0x180080010`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18001e680`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18001e6c4`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18001e753`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18001e829`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18001e680`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18001e6c4`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18001e753`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18001e829`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18001e694`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18001e767`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18001e83d`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18001e694`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18001e767`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18001e83d`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18001e6db`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18001e6db`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x18001e641`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x18001e81d`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x18001e8f2`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x18001e641`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x18001e81d`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x18001e8f2`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001e57a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001e65b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001e6ae`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001e90c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001e57a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001e65b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001e6ae`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001e90c`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall NgcHandler::AllocateAndCopyContainerStringProperty(__int64 **a1, unsigned int a2, void **a3)
{
  __int64 *v5; // rcx
  __int64 v6; // rax
  int v7; // ebx
  void *v8; // rcx
  void *v9; // rcx
  void *v11; // rbx
  HANDLE v12; // rax
  void *v13; // rcx
  SIZE_T v14; // rbx
  HANDLE ProcessHeap; // rax
  LPVOID v16; // rax
  void *v17; // rsi
  unsigned __int64 v18; // rdx
  __int64 v19; // rcx
  __int16 *v20; // r9
  _WORD *v21; // r8
  __int16 v22; // ax
  _WORD *v23; // rcx
  void *v24; // r14
  HANDLE v25; // rax
  HANDLE v26; // rax
  void *v27; // rcx
  LPVOID pv; // [rsp+30h] [rbp-59h] BYREF
  unsigned int v29; // [rsp+38h] [rbp-51h] BYREF
  unsigned int v30; // [rsp+3Ch] [rbp-4Dh] BYREF
  SIZE_T dwBytes; // [rsp+40h] [rbp-49h] BYREF
  EVENT_DESCRIPTOR EventDescriptor; // [rsp+48h] [rbp-41h] BYREF
  char v33; // [rsp+58h] [rbp-31h]
  unsigned int v34; // [rsp+60h] [rbp-29h] BYREF
  struct _EVENT_DATA_DESCRIPTOR UserData; // [rsp+70h] [rbp-19h] BYREF
  int *v36; // [rsp+80h] [rbp-9h]
  int v37; // [rsp+88h] [rbp-1h]
  int v38; // [rsp+8Ch] [rbp+3h]
  unsigned int *v39; // [rsp+90h] [rbp+7h]
  __int64 v40; // [rsp+98h] [rbp+Fh]
  int *v41; // [rsp+A0h] [rbp+17h]
  __int64 v42; // [rsp+A8h] [rbp+1Fh]

  pv = 0;
  LODWORD(dwBytes) = 0;
  v5 = *a1;
  v6 = *v5;
  *(_QWORD *)&EventDescriptor.Id = &pv;
  EventDescriptor.Keyword = 0;
  v33 = 1;
  v7 = (*(__int64 (__fastcall **)(__int64 *, _QWORD, ULONGLONG *, SIZE_T *))(v6 + 120))(
         v5,
         a2,
         &EventDescriptor.Keyword,
         &dwBytes);
  if ( v33 )
  {
    v8 = **(void ***)&EventDescriptor.Id;
    **(_QWORD **)&EventDescriptor.Id = EventDescriptor.Keyword;
    if ( v8 )
      CoTaskMemFree(v8);
  }
  if ( v7 < 0 )
  {
    if ( (unsigned int)dword_1800BE0B8 > 2 )
    {
      v34 = a2;
      v29 = v7;
      v41 = (int *)&v34;
      v42 = 4;
      v39 = &v29;
      v40 = 4;
      *(_DWORD *)&EventDescriptor.Id = 184549376;
      *(_DWORD *)&EventDescriptor.Level = 2;
      EventDescriptor.Keyword = 0;
      UserData.Ptr = (ULONGLONG)off_1800BE0C0;
      UserData.Size = *(unsigned __int16 *)off_1800BE0C0;
      UserData.Reserved = 2;
      v36 = (int *)byte_1800A9BD5;
      v37 = 63;
      v38 = 1;
      v30 = (unsigned int)&TraceLoggingMetadataEnd - (unsigned int)&TraceLoggingMetadata;
      EventWriteTransfer(RegHandle, &EventDescriptor, 0, 0, 4u, &UserData);
    }
LABEL_7:
    v9 = pv;
    pv = 0;
    if ( v9 )
      CoTaskMemFree(v9);
    return (unsigned int)v7;
  }
  if ( (_DWORD)dwBytes )
  {
    v14 = (unsigned int)dwBytes;
    ProcessHeap = GetProcessHeap();
    v16 = HeapAlloc(ProcessHeap, 8u, v14);
    v17 = v16;
    if ( v16 )
    {
      v18 = (unsigned __int64)(unsigned int)dwBytes >> 1;
      if ( v18 )
      {
        v19 = 2147483646;
        v20 = (__int16 *)pv;
        v21 = v16;
        do
        {
          if ( !v19 )
            break;
          v22 = *v20;
          if ( !*v20 )
            break;
          ++v20;
          *v21++ = v22;
          --v19;
          --v18;
        }
        while ( v18 );
        v7 = -2147024774;
        if ( v18 )
          v7 = 0;
        v23 = v21 - 1;
        if ( v18 )
          v23 = v21;
        *v23 = 0;
        if ( v18 )
        {
          v24 = *a3;
          *a3 = v17;
          if ( v24 )
          {
            v25 = GetProcessHeap();
            HeapFree(v25, 0, v24);
          }
          goto LABEL_7;
        }
      }
      else
      {
        v7 = -2147024809;
      }
      if ( (unsigned int)dword_1800BE0B8 > 2 )
      {
        v30 = v7;
        v39 = &v30;
        v40 = 4;
        *(_DWORD *)&EventDescriptor.Id = 184549376;
        *(_DWORD *)&EventDescriptor.Level = 2;
        EventDescriptor.Keyword = 0;
        UserData.Ptr = (ULONGLONG)off_1800BE0C0;
        UserData.Size = *(unsigned __int16 *)off_1800BE0C0;
        UserData.Reserved = 2;
        v36 = &dword_1800A9B7C;
        v37 = 25;
        v38 = 1;
        v29 = (unsigned int)&TraceLoggingMetadataEnd - (unsigned int)&TraceLoggingMetadata;
        EventWriteTransfer(RegHandle, &EventDescriptor, 0, 0, 3u, &UserData);
      }
      v26 = GetProcessHeap();
      HeapFree(v26, 0, v17);
      goto LABEL_7;
    }
    if ( (unsigned int)dword_1800BE0B8 > 2 )
    {
      v30 = -2147024882;
      v39 = &v30;
      v40 = 4;
      *(_DWORD *)&EventDescriptor.Id = 184549376;
      *(_DWORD *)&EventDescriptor.Level = 2;
      EventDescriptor.Keyword = 0;
      UserData.Ptr = (ULONGLONG)off_1800BE0C0;
      UserData.Size = *(unsigned __int16 *)off_1800BE0C0;
      UserData.Reserved = 2;
      v36 = &dword_1800A9C54;
      v37 = 48;
      v38 = 1;
      v29 = (unsigned int)&TraceLoggingMetadataEnd - (unsigned int)&TraceLoggingMetadata;
      EventWriteTransfer(RegHandle, &EventDescriptor, 0, 0, 3u, &UserData);
    }
    v27 = pv;
    pv = 0;
    if ( v27 )
      CoTaskMemFree(v27);
    return 2147942414LL;
  }
  else
  {
    v11 = *a3;
    *a3 = 0;
    if ( v11 )
    {
      v12 = GetProcessHeap();
      HeapFree(v12, 0, v11);
    }
    v13 = pv;
    pv = 0;
    if ( v13 )
      CoTaskMemFree(v13);
    return 0;
  }
}

```

## disassembly

```asm
0x18001e500  mov     [rsp-8+arg_18], rbx
0x18001e505  push    rbp
0x18001e506  push    rsi
0x18001e507  push    rdi
0x18001e508  push    r14
0x18001e50a  push    r15
0x18001e50c  lea     rbp, [rsp-37h]
0x18001e511  sub     rsp, 0C0h
0x18001e518  mov     rax, cs:__security_cookie
0x18001e51f  xor     rax, rsp
0x18001e522  mov     [rbp+57h+var_30], rax
0x18001e526  mov     rdi, r8
0x18001e529  mov     esi, edx
0x18001e52b  xor     r15d, r15d
0x18001e52e  mov     [rbp+57h+pv], r15
0x18001e532  mov     dword ptr [rbp+57h+dwBytes], r15d
0x18001e536  mov     rcx, [rcx]
0x18001e539  mov     rax, [rcx]
0x18001e53c  lea     rdx, [rbp+57h+pv]
0x18001e540  mov     qword ptr [rbp+57h+EventDescriptor.Id], rdx
0x18001e544  mov     [rbp+57h+EventDescriptor.Keyword], r15
0x18001e548  mov     [rbp+57h+var_88], 1
0x18001e54c  lea     r9, [rbp+57h+dwBytes]
0x18001e550  lea     r8, [rbp+57h+EventDescriptor.Keyword]
0x18001e554  mov     edx, esi
0x18001e556  mov     rax, [rax+78h]
0x18001e55a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001e55f  mov     ebx, eax
0x18001e561  cmp     [rbp+57h+var_88], r15b
0x18001e565  jz      short loc_18001E586
0x18001e567  mov     r8, qword ptr [rbp+57h+EventDescriptor.Id]
0x18001e56b  mov     rcx, [r8]; pv
0x18001e56e  mov     rdx, [rbp+57h+EventDescriptor.Keyword]
0x18001e572  mov     [r8], rdx
0x18001e575  test    rcx, rcx
0x18001e578  jz      short loc_18001E586
0x18001e57a  call    cs:__imp_CoTaskMemFree
0x18001e581  nop     dword ptr [rax+rax+00h]
0x18001e586  test    ebx, ebx
0x18001e588  jns     loc_18001E66E
0x18001e58e  mov     eax, cs:dword_1800BE0B8
0x18001e594  cmp     eax, 2
0x18001e597  jbe     loc_18001E64E
0x18001e59d  mov     [rbp+57h+var_80], esi
0x18001e5a0  mov     [rbp+57h+var_A8], ebx
0x18001e5a3  lea     rax, [rbp+57h+var_80]
0x18001e5a7  mov     [rbp+57h+var_40], rax
0x18001e5ab  mov     [rbp+57h+var_38], 4
0x18001e5b3  lea     rax, [rbp+57h+var_A8]
0x18001e5b7  mov     [rbp+57h+var_50], rax
0x18001e5bb  mov     [rbp+57h+var_48], 4
0x18001e5c3  mov     dword ptr [rbp+57h+EventDescriptor.Id], 0B000000h
0x18001e5ca  movzx   eax, cs:word_1800A9BCB
0x18001e5d1  mov     dword ptr [rbp+57h+EventDescriptor.Level], eax
0x18001e5d4  mov     [rbp+57h+EventDescriptor.Keyword], r15
0x18001e5d8  mov     rax, cs:off_1800BE0C0
0x18001e5df  mov     [rbp+57h+var_70.Ptr], rax
0x18001e5e3  movzx   eax, word ptr [rax]
0x18001e5e6  mov     [rbp+57h+var_70.Size], eax
0x18001e5e9  mov     dword ptr [rbp+57h+var_70.0Ch], 2
0x18001e5f0  lea     rax, byte_1800A9BD5
0x18001e5f7  mov     [rbp+57h+var_60], rax
0x18001e5fb  mov     [rbp+57h+var_58], 3Fh ; '?'
0x18001e602  mov     [rbp+57h+var_54], 1
0x18001e609  lea     rax, _TraceLoggingMetadataEnd
0x18001e610  lea     rcx, _TraceLoggingMetadata
0x18001e617  sub     eax, ecx
0x18001e619  mov     [rbp+57h+var_A4], eax
0x18001e61c  mov     eax, [rbp+57h+var_A4]
0x18001e61f  lea     rax, [rbp+57h+var_70]
0x18001e623  mov     [rsp+0E0h+UserData], rax; UserData
0x18001e628  mov     [rsp+0E0h+UserDataCount], 4; UserDataCount
0x18001e630  xor     r9d, r9d; RelatedActivityId
0x18001e633  xor     r8d, r8d; ActivityId
0x18001e636  lea     rdx, [rbp+57h+EventDescriptor]; EventDescriptor
0x18001e63a  mov     rcx, cs:RegHandle; RegHandle
0x18001e641  call    cs:__imp_EventWriteTransfer
0x18001e648  nop     dword ptr [rax+rax+00h]
0x18001e64d  nop
0x18001e64e  mov     rcx, [rbp+57h+pv]; pv
0x18001e652  mov     [rbp+57h+pv], r15
0x18001e656  test    rcx, rcx
0x18001e659  jz      short loc_18001E667
0x18001e65b  call    cs:__imp_CoTaskMemFree
0x18001e662  nop     dword ptr [rax+rax+00h]
0x18001e667  mov     eax, ebx
0x18001e669  jmp     loc_18001E91D
0x18001e66e  mov     eax, dword ptr [rbp+57h+dwBytes]
0x18001e671  test    eax, eax
0x18001e673  jnz     short loc_18001E6C1
0x18001e675  mov     rbx, [rdi]
0x18001e678  mov     [rdi], r15
0x18001e67b  test    rbx, rbx
0x18001e67e  jz      short loc_18001E6A1
0x18001e680  call    cs:__imp_GetProcessHeap
0x18001e687  nop     dword ptr [rax+rax+00h]
0x18001e68c  mov     rcx, rax; hHeap
0x18001e68f  mov     r8, rbx; lpMem
0x18001e692  xor     edx, edx; dwFlags
0x18001e694  call    cs:__imp_HeapFree
0x18001e69b  nop     dword ptr [rax+rax+00h]
0x18001e6a0  nop
0x18001e6a1  mov     rcx, [rbp+57h+pv]; pv
0x18001e6a5  mov     [rbp+57h+pv], r15
0x18001e6a9  test    rcx, rcx
0x18001e6ac  jz      short loc_18001E6BA
0x18001e6ae  call    cs:__imp_CoTaskMemFree
0x18001e6b5  nop     dword ptr [rax+rax+00h]
0x18001e6ba  xor     eax, eax
0x18001e6bc  jmp     loc_18001E91D
0x18001e6c1  mov     rbx, rax
0x18001e6c4  call    cs:__imp_GetProcessHeap
0x18001e6cb  nop     dword ptr [rax+rax+00h]
0x18001e6d0  mov     rcx, rax; hHeap
0x18001e6d3  mov     r8, rbx; dwBytes
0x18001e6d6  mov     edx, 8; dwFlags
0x18001e6db  call    cs:__imp_HeapAlloc
0x18001e6e2  nop     dword ptr [rax+rax+00h]
0x18001e6e7  mov     rsi, rax
0x18001e6ea  test    rax, rax
0x18001e6ed  jz      loc_18001E84E
0x18001e6f3  mov     edx, dword ptr [rbp+57h+dwBytes]
0x18001e6f6  shr     rdx, 1
0x18001e6f9  jz      short loc_18001E778
0x18001e6fb  mov     ecx, 7FFFFFFEh
0x18001e700  mov     r9, [rbp+57h+pv]
0x18001e704  mov     r8, rax
0x18001e707  test    rcx, rcx
0x18001e70a  jz      short loc_18001E72A
0x18001e70c  movzx   eax, word ptr [r9]
0x18001e710  test    ax, ax
0x18001e713  jz      short loc_18001E72A
0x18001e715  add     r9, 2
0x18001e719  mov     [r8], ax
0x18001e71d  add     r8, 2
0x18001e721  dec     rcx
0x18001e724  sub     rdx, 1
0x18001e728  jnz     short loc_18001E707
0x18001e72a  mov     ebx, 8007007Ah
0x18001e72f  test    rdx, rdx
0x18001e732  cmovnz  ebx, r15d
0x18001e736  lea     rcx, [r8-2]
0x18001e73a  cmovnz  rcx, r8
0x18001e73e  mov     [rcx], r15w
0x18001e742  jz      short loc_18001E77D
0x18001e744  mov     r14, [rdi]
0x18001e747  mov     [rdi], rsi
0x18001e74a  test    r14, r14
0x18001e74d  jz      loc_18001E64E
0x18001e753  call    cs:__imp_GetProcessHeap
0x18001e75a  nop     dword ptr [rax+rax+00h]
0x18001e75f  mov     rcx, rax; hHeap
0x18001e762  mov     r8, r14; lpMem
0x18001e765  xor     edx, edx; dwFlags
0x18001e767  call    cs:__imp_HeapFree
0x18001e76e  nop     dword ptr [rax+rax+00h]
0x18001e773  jmp     loc_18001E64E
0x18001e778  mov     ebx, 80070057h
0x18001e77d  mov     eax, cs:dword_1800BE0B8
0x18001e783  cmp     eax, 2
0x18001e786  jbe     loc_18001E829
0x18001e78c  mov     [rbp+57h+var_A4], ebx
0x18001e78f  lea     rax, [rbp+57h+var_A4]
0x18001e793  mov     [rbp+57h+var_50], rax
0x18001e797  mov     [rbp+57h+var_48], 4
0x18001e79f  mov     dword ptr [rbp+57h+EventDescriptor.Id], 0B000000h
0x18001e7a6  movzx   eax, cs:word_1800A9B72
0x18001e7ad  mov     dword ptr [rbp+57h+EventDescriptor.Level], eax
0x18001e7b0  mov     [rbp+57h+EventDescriptor.Keyword], r15
0x18001e7b4  mov     rax, cs:off_1800BE0C0
0x18001e7bb  mov     [rbp+57h+var_70.Ptr], rax
0x18001e7bf  movzx   eax, word ptr [rax]
0x18001e7c2  mov     [rbp+57h+var_70.Size], eax
0x18001e7c5  mov     dword ptr [rbp+57h+var_70.0Ch], 2
0x18001e7cc  lea     rax, dword_1800A9B7C
0x18001e7d3  mov     [rbp+57h+var_60], rax
0x18001e7d7  mov     [rbp+57h+var_58], 19h
0x18001e7de  mov     [rbp+57h+var_54], 1
0x18001e7e5  lea     rax, _TraceLoggingMetadataEnd
0x18001e7ec  lea     rcx, _TraceLoggingMetadata
0x18001e7f3  sub     eax, ecx
0x18001e7f5  mov     [rbp+57h+var_A8], eax
0x18001e7f8  mov     eax, [rbp+57h+var_A8]
0x18001e7fb  lea     rax, [rbp+57h+var_70]
0x18001e7ff  mov     [rsp+0E0h+UserData], rax; UserData
0x18001e804  mov     [rsp+0E0h+UserDataCount], 3; UserDataCount
0x18001e80c  xor     r9d, r9d; RelatedActivityId
0x18001e80f  xor     r8d, r8d; ActivityId
0x18001e812  lea     rdx, [rbp+57h+EventDescriptor]; EventDescriptor
0x18001e816  mov     rcx, cs:RegHandle; RegHandle
0x18001e81d  call    cs:__imp_EventWriteTransfer
0x18001e824  nop     dword ptr [rax+rax+00h]
0x18001e829  call    cs:__imp_GetProcessHeap
0x18001e830  nop     dword ptr [rax+rax+00h]
0x18001e835  mov     rcx, rax; hHeap
0x18001e838  mov     r8, rsi; lpMem
0x18001e83b  xor     edx, edx; dwFlags
0x18001e83d  call    cs:__imp_HeapFree
0x18001e844  nop     dword ptr [rax+rax+00h]
0x18001e849  jmp     loc_18001E64E
0x18001e84e  mov     eax, cs:dword_1800BE0B8
0x18001e854  cmp     eax, 2
0x18001e857  jbe     loc_18001E8FF
0x18001e85d  mov     [rbp+57h+var_A4], 8007000Eh
0x18001e864  lea     rax, [rbp+57h+var_A4]
0x18001e868  mov     [rbp+57h+var_50], rax
0x18001e86c  mov     [rbp+57h+var_48], 4
0x18001e874  mov     dword ptr [rbp+57h+EventDescriptor.Id], 0B000000h
0x18001e87b  movzx   eax, cs:word_1800A9C4A
0x18001e882  mov     dword ptr [rbp+57h+EventDescriptor.Level], eax
0x18001e885  mov     [rbp+57h+EventDescriptor.Keyword], r15
0x18001e889  mov     rax, cs:off_1800BE0C0
0x18001e890  mov     [rbp+57h+var_70.Ptr], rax
0x18001e894  movzx   eax, word ptr [rax]
0x18001e897  mov     [rbp+57h+var_70.Size], eax
0x18001e89a  mov     dword ptr [rbp+57h+var_70.0Ch], 2
0x18001e8a1  lea     rax, dword_1800A9C54
0x18001e8a8  mov     [rbp+57h+var_60], rax
0x18001e8ac  mov     [rbp+57h+var_58], 30h ; '0'
0x18001e8b3  mov     [rbp+57h+var_54], 1
0x18001e8ba  lea     rax, _TraceLoggingMetadataEnd
0x18001e8c1  lea     rcx, _TraceLoggingMetadata
0x18001e8c8  sub     eax, ecx
0x18001e8ca  mov     [rbp+57h+var_A8], eax
0x18001e8cd  mov     eax, [rbp+57h+var_A8]
0x18001e8d0  lea     rax, [rbp+57h+var_70]
0x18001e8d4  mov     [rsp+0E0h+UserData], rax; UserData
0x18001e8d9  mov     [rsp+0E0h+UserDataCount], 3; UserDataCount
0x18001e8e1  xor     r9d, r9d; RelatedActivityId
0x18001e8e4  xor     r8d, r8d; ActivityId
0x18001e8e7  lea     rdx, [rbp+57h+EventDescriptor]; EventDescriptor
0x18001e8eb  mov     rcx, cs:RegHandle; RegHandle
0x18001e8f2  call    cs:__imp_EventWriteTransfer
0x18001e8f9  nop     dword ptr [rax+rax+00h]
0x18001e8fe  nop
0x18001e8ff  mov     rcx, [rbp+57h+pv]; pv
0x18001e903  mov     [rbp+57h+pv], r15
0x18001e907  test    rcx, rcx
0x18001e90a  jz      short loc_18001E918
0x18001e90c  call    cs:__imp_CoTaskMemFree
0x18001e913  nop     dword ptr [rax+rax+00h]
0x18001e918  mov     eax, 8007000Eh
0x18001e91d  mov     rcx, [rbp+57h+var_30]
0x18001e921  xor     rcx, rsp; StackCookie
0x18001e924  call    __security_check_cookie
0x18001e929  mov     rbx, [rsp+0E0h+arg_18]
0x18001e931  add     rsp, 0C0h
0x18001e938  pop     r15
0x18001e93a  pop     r14
0x18001e93c  pop     rdi
0x18001e93d  pop     rsi
0x18001e93e  pop     rbp
0x18001e93f  retn
```
