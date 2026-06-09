# SuCreatePool(_SP_POOL_INFO *,_LIST_ENTRY *,int (*)(_SU_OPERATION,_LIST_ENTRY *,void *,void *,void *,void *),void *,_SU_POOL_OBJECT * *)

- ea: `0x14000a8dc`
- end: `0x14000ad58`
- name: `?SuCreatePool@@YAHPEAU_SP_POOL_INFO@@PEAU_LIST_ENTRY@@P6AHW4_SU_OPERATION@@1PEAX333@Z3PEAPEAU_SU_POOL_OBJECT@@@Z`
- size: `1148`
- prototype: `__int64 __fastcall(struct _SP_POOL_INFO *, struct _LIST_ENTRY *, int (__high *)(enum _SU_OPERATION, struct _LIST_ENTRY *, void *, void *, void *, void *), void *, struct _SU_POOL_OBJECT **)`
- caller_count: `1`
- callee_count: `14`
- tags: `broker_com_uri`

## callers

- `0x140014e74`

## callees

- `0x140001caf`
- `0x140004114`
- `0x14000a440`
- `0x14000a6f8`
- `0x14000a8dc`
- `0x14000b7ec`
- `0x14000ba08`
- `0x14000bb78`
- `0x14000c954`
- `0x14000ce60`
- `0x14000d9cc`
- `0x14000dac4`
- `0x14001edc0`
- `0x140020010`

## import_xrefs

- `KERNEL32!LocalFree` at `0x14000ad1b`
- `KERNEL32!LocalFree` at `0x14000ad1b`
- `KERNEL32!SetLastError` at `0x14000a977`
- `KERNEL32!SetLastError` at `0x14000a9da`
- `KERNEL32!SetLastError` at `0x14000ad29`
- `KERNEL32!SetLastError` at `0x14000a977`
- `KERNEL32!SetLastError` at `0x14000a9da`
- `KERNEL32!SetLastError` at `0x14000ad29`
- `KERNEL32!GetLastError` at `0x14000ab4e`
- `KERNEL32!GetLastError` at `0x14000ab4e`
- `KERNEL32!QueryPerformanceCounter` at `0x14000a959`
- `KERNEL32!QueryPerformanceCounter` at `0x14000ab6b`
- `KERNEL32!QueryPerformanceCounter` at `0x14000a959`
- `KERNEL32!QueryPerformanceCounter` at `0x14000ab6b`
- `KERNEL32!DeviceIoControl` at `0x14000aacb`
- `KERNEL32!DeviceIoControl` at `0x14000ab13`
- `KERNEL32!DeviceIoControl` at `0x14000aacb`
- `KERNEL32!DeviceIoControl` at `0x14000ab13`

## string_xrefs

- `0x14000ab1f`: `DeviceIoControl - IOCTL_SPACEPORT_CREATE_POOL`

## pseudocode

```c
__int64 __fastcall SuCreatePool(
        struct _SP_POOL_INFO *a1,
        struct _LIST_ENTRY *a2,
        int (__high *a3)(enum _SU_OPERATION, struct _LIST_ENTRY *, void *, void *, void *, void *),
        void *a4,
        struct _SU_POOL_OBJECT **a5)
{
  struct _LIST_ENTRY *Flink; // rax
  __int64 (__fastcall *v8)(int, struct _LIST_ENTRY *, struct _SP_POOL_INFO *, unsigned __int8, unsigned int); // rbx
  const char *v9; // r15
  unsigned int Pool; // esi
  _DWORD *v11; // rdi
  struct _GUID *v12; // r12
  __int128 v13; // xmm0
  DWORD v14; // r9d
  DWORD LastError; // eax
  int v16; // edx
  int v17; // r8d
  int v18; // r9d
  HLOCAL v19; // r15
  char *v20; // rcx
  DWORD v21; // r13d
  struct _LIST_ENTRY *v22; // rax
  struct _LIST_ENTRY *v23; // rcx
  struct _LIST_ENTRY *Blink; // rdx
  struct _LIST_ENTRY **v25; // rdx
  struct _LIST_ENTRY *v26; // rax
  __int64 v27; // rcx
  struct _LIST_ENTRY *v28; // rcx
  int lpOutBuffer; // [rsp+20h] [rbp-E0h]
  __int64 v31; // [rsp+48h] [rbp-B8h]
  DWORD BytesReturned; // [rsp+60h] [rbp-A0h] BYREF
  int v33; // [rsp+64h] [rbp-9Ch]
  __int128 v34; // [rsp+68h] [rbp-98h] BYREF
  HLOCAL hMem; // [rsp+78h] [rbp-88h] BYREF
  DWORD lpBytesReturned; // [rsp+80h] [rbp-80h] BYREF
  LARGE_INTEGER PerformanceCount; // [rsp+88h] [rbp-78h] BYREF
  LARGE_INTEGER v38; // [rsp+90h] [rbp-70h] BYREF
  __int64 v39; // [rsp+98h] [rbp-68h]
  _OWORD v40[2]; // [rsp+A0h] [rbp-60h] BYREF
  __int64 v41; // [rsp+C0h] [rbp-40h]
  int InBuffer; // [rsp+D0h] [rbp-30h] BYREF
  __int128 v43; // [rsp+D4h] [rbp-2Ch]
  __int64 v44; // [rsp+F8h] [rbp-8h]
  __int64 v45; // [rsp+100h] [rbp+0h]
  char v46; // [rsp+108h] [rbp+8h]

  memset_0(&InBuffer, 0, 0x50u);
  memset(v40, 0, sizeof(v40));
  v41 = 0;
  lpBytesReturned = 0;
  v34 = 0;
  hMem = 0;
  v33 = 0;
  SI_TIMER::SI_TIMER((SI_TIMER *)&PerformanceCount);
  *a5 = 0;
  QueryPerformanceCounter(&PerformanceCount);
  Flink = a2->Flink;
  LODWORD(v40[0]) = 40;
  BYTE4(v41) = 0;
  if ( Flink == a2 )
  {
    SetLastError(0x57u);
    v8 = 0;
    v9 = "Empty DriveListHead invalid";
    Pool = 0;
    v11 = (_DWORD *)((char *)a1 + 2588);
LABEL_23:
    LastError = GetLastError();
    v12 = (struct _GUID *)((char *)a1 + 8);
    goto LABEL_25;
  }
  v9 = 0;
  *((_QWORD *)&v34 + 1) = &v34;
  *(_QWORD *)&v34 = &v34;
  do
  {
    Flink[1].Flink = 0;
    Flink = Flink->Flink;
  }
  while ( Flink != a2 );
  v11 = (_DWORD *)((char *)a1 + 2588);
  if ( *((_DWORD *)a1 + 647) > 0x1Du
    && !(unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_SpacesPoolVersion2700>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_SpacesPoolVersion2700>::GetImpl'::`2'::impl) )
  {
    SetLastError(0x32u);
    Pool = 0;
LABEL_22:
    v8 = SiPerformParallelOperation;
    goto LABEL_23;
  }
  Pool = SiValidatePool(a1, 1);
  if ( !Pool )
  {
    v9 = "SiValidatePool";
    goto LABEL_22;
  }
  Pool = SiValidateDrives(a1, a2);
  if ( !Pool )
  {
    v9 = "SiValidateDrives";
    goto LABEL_22;
  }
  v33 = 1;
  Pool = SiPerformParallelOperation(1, a2, a1, 0, 0);
  if ( !Pool )
  {
    v9 = "Callback - SuOperationPrepareDrives";
    goto LABEL_22;
  }
  Pool = SiSetDrives(a2);
  if ( !Pool )
  {
    v9 = "SiSetDrives";
    goto LABEL_22;
  }
  InBuffer = 80;
  v12 = (struct _GUID *)((char *)a1 + 8);
  v44 = 0;
  v13 = *(_OWORD *)((char *)a1 + 8);
  v45 = 1;
  v46 = 1;
  v43 = v13;
  BytesReturned = 0;
  Pool = DeviceIoControl(Spaceport, 0xE7C018u, &InBuffer, 0x50u, 0, 0, &BytesReturned, 0);
  if ( !Pool )
  {
    v9 = "SuSetPoolAttributes";
    goto LABEL_22;
  }
  v14 = *((_DWORD *)a1 + 1);
  *((_QWORD *)a1 + 325) = 0;
  Pool = DeviceIoControl(Spaceport, 0xE7C010u, a1, v14, 0, 0, &lpBytesReturned, 0);
  if ( !Pool )
  {
    v9 = "DeviceIoControl - IOCTL_SPACEPORT_CREATE_POOL";
    goto LABEL_22;
  }
  v33 = 0;
  Pool = SiGetPool((struct _GUID *)((char *)a1 + 8), 0, a5);
  if ( !Pool )
  {
    v9 = "SuGetPool";
    goto LABEL_22;
  }
  LastError = 0;
  v8 = SiPerformParallelOperation;
LABEL_25:
  BytesReturned = LastError;
  QueryPerformanceCounter(&v38);
  SiIdsStringFromList(v12, a2, (unsigned __int16 **)&hMem);
  if ( Pool )
  {
    v19 = hMem;
    if ( (Microsoft_Windows_StorageSpaces_ApiEnableBits & 2) != 0 )
      McTemplateK0zsjzqzx_EventWriteTransfer(
        (_DWORD)a1 + 24,
        1000000 * (v38.QuadPart - PerformanceCount.QuadPart) % v39,
        v17,
        v18,
        lpOutBuffer,
        (__int64)v12,
        (__int64)a1 + 24,
        *v11,
        (__int64)hMem,
        1000000 * (v38.QuadPart - PerformanceCount.QuadPart) / v39);
  }
  else
  {
    if ( (Microsoft_Windows_StorageSpaces_ApiEnableBits & 1) != 0 )
    {
      v20 = (char *)a1 + 24;
      v21 = BytesReturned;
      v31 = (__int64)v9;
      v19 = hMem;
      McTemplateK0zsjzqzsq_EventWriteTransfer(
        (_DWORD)v20,
        v16,
        v17,
        v18,
        lpOutBuffer,
        (__int64)v12,
        (__int64)v20,
        *v11,
        (__int64)hMem,
        v31,
        BytesReturned);
      goto LABEL_32;
    }
    v19 = hMem;
  }
  v21 = BytesReturned;
LABEL_32:
  if ( v33 )
  {
    v22 = a2->Flink;
    if ( a2->Flink != a2 )
    {
      do
      {
        v23 = v22->Flink;
        if ( HIDWORD(v22[1].Flink) == 3 )
        {
          if ( v23->Blink != v22
            || (Blink = v22->Blink, Blink->Flink != v22)
            || (Blink->Flink = v23,
                v23->Blink = Blink,
                v25 = (struct _LIST_ENTRY **)*((_QWORD *)&v34 + 1),
                **((__int128 ***)&v34 + 1) != &v34) )
          {
LABEL_46:
            __fastfail(3u);
          }
          v22->Blink = (struct _LIST_ENTRY *)*((_QWORD *)&v34 + 1);
          v22->Flink = (struct _LIST_ENTRY *)&v34;
          *v25 = v22;
          *((_QWORD *)&v34 + 1) = v22;
        }
        v22 = v23;
      }
      while ( v23 != a2 );
    }
    ((void (__fastcall *)(__int64, __int128 *, _OWORD *, _QWORD, _QWORD, _QWORD))v8)(3, &v34, v40, 0, 0, 0);
    ((void (__fastcall *)(__int64, __int128 *, _QWORD))v8)(2, &v34, 0);
    while ( 1 )
    {
      v26 = (struct _LIST_ENTRY *)v34;
      if ( (__int128 *)v34 == &v34 )
        break;
      if ( *(__int128 **)(v34 + 8) != &v34 )
        goto LABEL_46;
      v27 = *(_QWORD *)v34;
      if ( *(_QWORD *)(*(_QWORD *)v34 + 8LL) != (_QWORD)v34 )
        goto LABEL_46;
      *(_QWORD *)&v34 = *(_QWORD *)v34;
      *(_QWORD *)(v27 + 8) = &v34;
      v28 = a2->Blink;
      if ( v28->Flink != a2 )
        goto LABEL_46;
      v26->Flink = a2;
      v26->Blink = v28;
      v28->Flink = v26;
      a2->Blink = v26;
    }
  }
  if ( v19 )
    LocalFree(v19);
  if ( v21 )
    SetLastError(v21);
  return Pool;
}

```

## disassembly

```asm
0x14000a8dc  mov     [rsp-8+arg_10], rbx
0x14000a8e1  push    rbp
0x14000a8e2  push    rsi
0x14000a8e3  push    rdi
0x14000a8e4  push    r12
0x14000a8e6  push    r13
0x14000a8e8  push    r14
0x14000a8ea  push    r15
0x14000a8ec  lea     rbp, [rsp-30h]
0x14000a8f1  sub     rsp, 130h
0x14000a8f8  mov     rax, cs:__security_cookie
0x14000a8ff  xor     rax, rsp
0x14000a902  mov     [rbp+60h+var_40], rax
0x14000a906  mov     rbx, [rbp+60h+arg_20]
0x14000a90d  mov     r14, rdx
0x14000a910  xor     edx, edx; Val
0x14000a912  mov     r13, rcx
0x14000a915  lea     rcx, [rbp+60h+InBuffer]; void *
0x14000a919  lea     r8d, [rdx+50h]; Size
0x14000a91d  call    memset_0
0x14000a922  xorps   xmm0, xmm0
0x14000a925  lea     rcx, [rbp+60h+PerformanceCount]; this
0x14000a929  xor     r12d, r12d
0x14000a92c  xor     eax, eax
0x14000a92e  movups  [rbp+60h+var_C0], xmm0
0x14000a932  mov     [rbp+60h+var_A0], rax
0x14000a936  movups  [rbp+60h+var_B0], xmm0
0x14000a93a  mov     [rbp+60h+var_E0], r12d
0x14000a93e  movups  [rsp+160h+var_F8], xmm0
0x14000a943  mov     [rsp+160h+hMem], r12
0x14000a948  mov     [rsp+160h+var_FC], r12d
0x14000a94d  call    ??0SI_TIMER@@QEAA@XZ; SI_TIMER::SI_TIMER(void)
0x14000a952  lea     rcx, [rbp+60h+PerformanceCount]; lpPerformanceCount
0x14000a956  mov     [rbx], r12
0x14000a959  call    cs:__imp_QueryPerformanceCounter
0x14000a95f  mov     rax, [r14]
0x14000a962  mov     dword ptr [rbp+60h+var_C0], 28h ; '('
0x14000a969  mov     byte ptr [rbp+60h+var_A0+4], r12b
0x14000a96d  cmp     rax, r14
0x14000a970  jnz     short loc_14000A996
0x14000a972  lea     ecx, [r12+57h]; dwErrCode
0x14000a977  call    cs:__imp_SetLastError
0x14000a97d  mov     ebx, r12d
0x14000a980  lea     r15, aEmptyDrivelist; "Empty DriveListHead invalid"
0x14000a987  mov     esi, r12d
0x14000a98a  lea     rdi, [r13+0A1Ch]
0x14000a991  jmp     loc_14000AB4E
0x14000a996  lea     rcx, [rsp+160h+var_F8]
0x14000a99b  mov     r15, r12
0x14000a99e  mov     qword ptr [rsp+160h+var_F8+8], rcx
0x14000a9a3  lea     rcx, [rsp+160h+var_F8]
0x14000a9a8  mov     qword ptr [rsp+160h+var_F8], rcx
0x14000a9ad  mov     [rax+10h], r12
0x14000a9b1  mov     rax, [rax]
0x14000a9b4  cmp     rax, r14
0x14000a9b7  jnz     short loc_14000A9AD
0x14000a9b9  lea     rdi, [r13+0A1Ch]
0x14000a9c0  cmp     dword ptr [rdi], 1Dh
0x14000a9c3  jbe     short loc_14000A9E8
0x14000a9c5  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_SpacesPoolVersion2700@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_SpacesPoolVersion2700@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_SpacesPoolVersion2700> `wil::Feature<__WilFeatureTraits_Feature_SpacesPoolVersion2700>::GetImpl(void)'::`2'::impl
0x14000a9cc  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_SpacesPoolVersion2700@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_SpacesPoolVersion2700>::__private_IsEnabled(void)
0x14000a9d1  test    al, al
0x14000a9d3  jnz     short loc_14000A9E8
0x14000a9d5  mov     ecx, 32h ; '2'; dwErrCode
0x14000a9da  call    cs:__imp_SetLastError
0x14000a9e0  mov     esi, r12d
0x14000a9e3  jmp     loc_14000AB47
0x14000a9e8  mov     edx, 1; int
0x14000a9ed  mov     rcx, r13; struct _SP_POOL_INFO *
0x14000a9f0  call    ?SiValidatePool@@YAHPEAU_SP_POOL_INFO@@H@Z; SiValidatePool(_SP_POOL_INFO *,int)
0x14000a9f5  mov     esi, eax
0x14000a9f7  test    eax, eax
0x14000a9f9  jnz     short loc_14000AA07
0x14000a9fb  lea     r15, aSivalidatepool; "SiValidatePool"
0x14000aa02  jmp     loc_14000AB47
0x14000aa07  mov     rdx, r14; struct _LIST_ENTRY *
0x14000aa0a  mov     rcx, r13; struct _SP_POOL_INFO *
0x14000aa0d  call    ?SiValidateDrives@@YAHPEAU_SP_POOL_INFO@@PEAU_LIST_ENTRY@@@Z; SiValidateDrives(_SP_POOL_INFO *,_LIST_ENTRY *)
0x14000aa12  mov     esi, eax
0x14000aa14  test    eax, eax
0x14000aa16  jnz     short loc_14000AA24
0x14000aa18  lea     r15, aSivalidatedriv; "SiValidateDrives"
0x14000aa1f  jmp     loc_14000AB47
0x14000aa24  xor     r9d, r9d
0x14000aa27  mov     qword ptr [rsp+160h+nOutBufferSize], r12
0x14000aa2c  mov     r8, r13
0x14000aa2f  mov     [rsp+160h+var_FC], 1
0x14000aa37  mov     rdx, r14
0x14000aa3a  mov     [rsp+160h+lpOutBuffer], r12
0x14000aa3f  lea     ecx, [r9+1]
0x14000aa43  call    ?SiPerformParallelOperation@@YAHW4_SU_OPERATION@@PEAU_LIST_ENTRY@@PEAX222@Z; SiPerformParallelOperation(_SU_OPERATION,_LIST_ENTRY *,void *,void *,void *,void *)
0x14000aa48  mov     esi, eax
0x14000aa4a  test    eax, eax
0x14000aa4c  jnz     short loc_14000AA5A
0x14000aa4e  lea     r15, aCallbackSuoper; "Callback - SuOperationPrepareDrives"
0x14000aa55  jmp     loc_14000AB47
0x14000aa5a  mov     rcx, r14; struct _LIST_ENTRY *
0x14000aa5d  call    ?SiSetDrives@@YAHPEAU_LIST_ENTRY@@@Z; SiSetDrives(_LIST_ENTRY *)
0x14000aa62  mov     esi, eax
0x14000aa64  test    eax, eax
0x14000aa66  jnz     short loc_14000AA74
0x14000aa68  lea     r15, aSisetdrives; "SiSetDrives"
0x14000aa6f  jmp     loc_14000AB47
0x14000aa74  xor     ecx, ecx
0x14000aa76  mov     [rbp+60h+InBuffer], 50h ; 'P'
0x14000aa7d  lea     r12, [r13+8]
0x14000aa81  mov     [rbp+60h+var_68], rcx
0x14000aa85  movups  xmm0, xmmword ptr [r12]
0x14000aa8a  mov     [rbp+60h+var_60], 1
0x14000aa92  mov     [rbp+60h+var_58], 1
0x14000aa96  movdqu  [rbp+60h+var_8C], xmm0
0x14000aa9b  mov     [rsp+160h+BytesReturned], ecx
0x14000aa9f  mov     [rsp+160h+lpOverlapped], rcx; lpOverlapped
0x14000aaa4  lea     rax, [rsp+160h+BytesReturned]
0x14000aaa9  mov     [rsp+160h+lpBytesReturned], rax; lpBytesReturned
0x14000aaae  lea     r9d, [rcx+50h]; nInBufferSize
0x14000aab2  mov     [rsp+160h+nOutBufferSize], ecx; nOutBufferSize
0x14000aab6  lea     r8, [rbp+60h+InBuffer]; lpInBuffer
0x14000aaba  mov     [rsp+160h+lpOutBuffer], rcx; lpOutBuffer
0x14000aabf  mov     edx, 0E7C018h; dwIoControlCode
0x14000aac4  mov     rcx, cs:?Spaceport@@3PEAXEA; hDevice
0x14000aacb  call    cs:__imp_DeviceIoControl
0x14000aad1  xor     ecx, ecx
0x14000aad3  mov     esi, eax
0x14000aad5  test    eax, eax
0x14000aad7  jnz     short loc_14000AAE2
0x14000aad9  lea     r15, aSusetpoolattri; "SuSetPoolAttributes"
0x14000aae0  jmp     short loc_14000AB47
0x14000aae2  mov     r9d, [r13+4]; nInBufferSize
0x14000aae6  lea     rax, [rbp+60h+var_E0]
0x14000aaea  mov     [rsp+160h+lpOverlapped], rcx; lpOverlapped
0x14000aaef  mov     r8, r13; lpInBuffer
0x14000aaf2  mov     [rsp+160h+lpBytesReturned], rax; lpBytesReturned
0x14000aaf7  mov     edx, 0E7C010h; dwIoControlCode
0x14000aafc  mov     [rsp+160h+nOutBufferSize], ecx; nOutBufferSize
0x14000ab00  mov     [rsp+160h+lpOutBuffer], rcx; lpOutBuffer
0x14000ab05  mov     [r13+0A28h], rcx
0x14000ab0c  mov     rcx, cs:?Spaceport@@3PEAXEA; hDevice
0x14000ab13  call    cs:__imp_DeviceIoControl
0x14000ab19  mov     esi, eax
0x14000ab1b  test    eax, eax
0x14000ab1d  jnz     short loc_14000AB28
0x14000ab1f  lea     r15, aDeviceiocontro_9; "DeviceIoControl - IOCTL_SPACEPORT_CREAT"...
0x14000ab26  jmp     short loc_14000AB47
0x14000ab28  mov     r8, rbx; struct _SU_POOL_OBJECT **
0x14000ab2b  mov     [rsp+160h+var_FC], r15d
0x14000ab30  xor     edx, edx; unsigned int
0x14000ab32  mov     rcx, r12; struct _GUID *
0x14000ab35  call    ?SiGetPool@@YAHPEAU_GUID@@KPEAPEAU_SU_POOL_OBJECT@@@Z; SiGetPool(_GUID *,ulong,_SU_POOL_OBJECT * *)
0x14000ab3a  mov     esi, eax
0x14000ab3c  test    eax, eax
0x14000ab3e  jnz     short loc_14000AB5A
0x14000ab40  lea     r15, aSugetpool; "SuGetPool"
0x14000ab47  lea     rbx, ?SiPerformParallelOperation@@YAHW4_SU_OPERATION@@PEAU_LIST_ENTRY@@PEAX222@Z; SiPerformParallelOperation(_SU_OPERATION,_LIST_ENTRY *,void *,void *,void *,void *)
0x14000ab4e  call    cs:__imp_GetLastError
0x14000ab54  lea     r12, [r13+8]
0x14000ab58  jmp     short loc_14000AB63
0x14000ab5a  xor     eax, eax
0x14000ab5c  lea     rbx, ?SiPerformParallelOperation@@YAHW4_SU_OPERATION@@PEAU_LIST_ENTRY@@PEAX222@Z; SiPerformParallelOperation(_SU_OPERATION,_LIST_ENTRY *,void *,void *,void *,void *)
0x14000ab63  lea     rcx, [rbp+60h+var_D0]; lpPerformanceCount
0x14000ab67  mov     [rsp+160h+BytesReturned], eax
0x14000ab6b  call    cs:__imp_QueryPerformanceCounter
0x14000ab71  lea     r8, [rsp+160h+hMem]; unsigned __int16 **
0x14000ab76  mov     rdx, r14; struct _LIST_ENTRY *
0x14000ab79  mov     rcx, r12; struct _GUID *
0x14000ab7c  call    ?SiIdsStringFromList@@YAHPEAU_GUID@@PEAU_LIST_ENTRY@@PEAPEAG@Z; SiIdsStringFromList(_GUID *,_LIST_ENTRY *,ushort * *)
0x14000ab81  test    esi, esi
0x14000ab83  jz      short loc_14000ABCD
0x14000ab85  test    cs:Microsoft_Windows_StorageSpaces_ApiEnableBits, 2
0x14000ab8c  mov     r15, [rsp+160h+hMem]
0x14000ab91  jz      short loc_14000AC0F
0x14000ab93  mov     rax, qword ptr [rbp+60h+var_D0]
0x14000ab97  lea     rcx, [r13+18h]
0x14000ab9b  sub     rax, qword ptr [rbp+60h+PerformanceCount]
0x14000ab9f  imul    rax, 0F4240h
0x14000aba6  cqo
0x14000aba8  idiv    [rbp+60h+var_C8]
0x14000abac  mov     [rsp+160h+var_118], rax
0x14000abb1  mov     eax, [rdi]
0x14000abb3  mov     [rsp+160h+var_120], r15
0x14000abb8  mov     dword ptr [rsp+160h+lpOverlapped], eax
0x14000abbc  mov     [rsp+160h+lpBytesReturned], rcx
0x14000abc1  mov     qword ptr [rsp+160h+nOutBufferSize], r12
0x14000abc6  call    McTemplateK0zsjzqzx_EventWriteTransfer
0x14000abcb  jmp     short loc_14000AC0F
0x14000abcd  test    cs:Microsoft_Windows_StorageSpaces_ApiEnableBits, 1
0x14000abd4  jz      short loc_14000AC0A
0x14000abd6  mov     eax, [rdi]
0x14000abd8  lea     rcx, [r13+18h]
0x14000abdc  mov     r13d, [rsp+160h+BytesReturned]
0x14000abe1  mov     [rsp+160h+var_110], r13d
0x14000abe6  mov     [rsp+160h+var_118], r15
0x14000abeb  mov     r15, [rsp+160h+hMem]
0x14000abf0  mov     [rsp+160h+var_120], r15
0x14000abf5  mov     dword ptr [rsp+160h+lpOverlapped], eax
0x14000abf9  mov     [rsp+160h+lpBytesReturned], rcx
0x14000abfe  mov     qword ptr [rsp+160h+nOutBufferSize], r12
0x14000ac03  call    McTemplateK0zsjzqzsq_EventWriteTransfer
0x14000ac08  jmp     short loc_14000AC14
0x14000ac0a  mov     r15, [rsp+160h+hMem]
0x14000ac0f  mov     r13d, [rsp+160h+BytesReturned]
0x14000ac14  xor     edi, edi
0x14000ac16  cmp     [rsp+160h+var_FC], edi
0x14000ac1a  jz      loc_14000AD13
0x14000ac20  mov     rax, [r14]
0x14000ac23  lea     r12d, [rdi+3]
0x14000ac27  cmp     rax, r14
0x14000ac2a  jz      short loc_14000AC82
0x14000ac2c  mov     rcx, [rax]
0x14000ac2f  cmp     [rax+14h], r12d
0x14000ac33  jnz     short loc_14000AC7A
0x14000ac35  cmp     [rcx+8], rax
0x14000ac39  jnz     loc_14000AD0E
0x14000ac3f  mov     rdx, [rax+8]
0x14000ac43  cmp     [rdx], rax
0x14000ac46  jnz     loc_14000AD0E
0x14000ac4c  mov     [rdx], rcx
0x14000ac4f  lea     r8, [rsp+160h+var_F8]
0x14000ac54  mov     [rcx+8], rdx
0x14000ac58  mov     rdx, qword ptr [rsp+160h+var_F8+8]
0x14000ac5d  cmp     [rdx], r8
0x14000ac60  jnz     loc_14000AD0E
0x14000ac66  mov     [rax+8], rdx
0x14000ac6a  lea     r8, [rsp+160h+var_F8]
0x14000ac6f  mov     [rax], r8
0x14000ac72  mov     [rdx], rax
0x14000ac75  mov     qword ptr [rsp+160h+var_F8+8], rax
0x14000ac7a  mov     rax, rcx
0x14000ac7d  cmp     rcx, r14
0x14000ac80  jnz     short loc_14000AC2C
0x14000ac82  mov     qword ptr [rsp+160h+nOutBufferSize], rdi
0x14000ac87  lea     r8, [rbp+60h+var_C0]
0x14000ac8b  xor     r9d, r9d
0x14000ac8e  mov     [rsp+160h+lpOutBuffer], rdi
0x14000ac93  lea     rdx, [rsp+160h+var_F8]
0x14000ac98  mov     ecx, r12d
0x14000ac9b  mov     rax, rbx
0x14000ac9e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000aca3  xor     r9d, r9d
0x14000aca6  mov     qword ptr [rsp+160h+nOutBufferSize], rdi
0x14000acab  xor     r8d, r8d
0x14000acae  mov     [rsp+160h+lpOutBuffer], rdi
0x14000acb3  lea     rdx, [rsp+160h+var_F8]
0x14000acb8  mov     rax, rbx
0x14000acbb  lea     ecx, [r9+2]
0x14000acbf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000acc4  mov     rax, qword ptr [rsp+160h+var_F8]
0x14000acc9  lea     rcx, [rsp+160h+var_F8]
0x14000acce  cmp     rax, rcx
0x14000acd1  jz      short loc_14000AD13
0x14000acd3  lea     rcx, [rsp+160h+var_F8]
0x14000acd8  cmp     [rax+8], rcx
0x14000acdc  jnz     short loc_14000AD0E
0x14000acde  mov     rcx, [rax]
0x14000ace1  cmp     [rcx+8], rax
0x14000ace5  jnz     short loc_14000AD0E
0x14000ace7  mov     qword ptr [rsp+160h+var_F8], rcx
0x14000acec  lea     rdx, [rsp+160h+var_F8]
0x14000acf1  mov     [rcx+8], rdx
0x14000acf5  mov     rcx, [r14+8]
0x14000acf9  cmp     [rcx], r14
0x14000acfc  jnz     short loc_14000AD0E
0x14000acfe  mov     [rax], r14
0x14000ad01  mov     [rax+8], rcx
0x14000ad05  mov     [rcx], rax
0x14000ad08  mov     [r14+8], rax
0x14000ad0c  jmp     short loc_14000ACC4
0x14000ad0e  mov     rcx, r12
0x14000ad11  int     29h; Win8: RtlFailFast(ecx)
0x14000ad13  test    r15, r15
0x14000ad16  jz      short loc_14000AD21
0x14000ad18  mov     rcx, r15; hMem
0x14000ad1b  call    cs:__imp_LocalFree
0x14000ad21  test    r13d, r13d
0x14000ad24  jz      short loc_14000AD2F
0x14000ad26  mov     ecx, r13d; dwErrCode
0x14000ad29  call    cs:__imp_SetLastError
0x14000ad2f  mov     eax, esi
0x14000ad31  mov     rcx, [rbp+60h+var_40]
0x14000ad35  xor     rcx, rsp; StackCookie
0x14000ad38  call    __security_check_cookie
0x14000ad3d  mov     rbx, [rsp+160h+arg_10]
0x14000ad45  add     rsp, 130h
0x14000ad4c  pop     r15
0x14000ad4e  pop     r14
0x14000ad50  pop     r13
0x14000ad52  pop     r12
0x14000ad54  pop     rdi
0x14000ad55  pop     rsi
0x14000ad56  pop     rbp
0x14000ad57  retn
```
