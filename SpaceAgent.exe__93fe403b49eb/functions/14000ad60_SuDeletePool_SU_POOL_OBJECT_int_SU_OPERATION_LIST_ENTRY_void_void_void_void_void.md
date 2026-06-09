# SuDeletePool(_SU_POOL_OBJECT *,int (*)(_SU_OPERATION,_LIST_ENTRY *,void *,void *,void *,void *),void *)

- ea: `0x14000ad60`
- end: `0x14000af5a`
- name: `?SuDeletePool@@YAHPEAU_SU_POOL_OBJECT@@P6AHW4_SU_OPERATION@@PEAU_LIST_ENTRY@@PEAX333@Z3@Z`
- size: `506`
- prototype: `__int64 __fastcall(struct _SU_POOL_OBJECT *, int (__high *)(enum _SU_OPERATION, struct _LIST_ENTRY *, void *, void *, void *, void *), void *)`
- caller_count: `1`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x1400152c8`

## callees

- `0x140004114`
- `0x14000ad60`
- `0x14000b828`
- `0x14000b934`
- `0x14000c26c`
- `0x14000ce60`

## import_xrefs

- `KERNEL32!LocalFree` at `0x14000af28`
- `KERNEL32!LocalFree` at `0x14000af28`
- `KERNEL32!SetLastError` at `0x14000af3d`
- `KERNEL32!SetLastError` at `0x14000af3d`
- `KERNEL32!GetLastError` at `0x14000ae75`
- `KERNEL32!GetLastError` at `0x14000ae75`
- `KERNEL32!QueryPerformanceCounter` at `0x14000ad98`
- `KERNEL32!QueryPerformanceCounter` at `0x14000ae81`
- `KERNEL32!QueryPerformanceCounter` at `0x14000ad98`
- `KERNEL32!QueryPerformanceCounter` at `0x14000ae81`
- `KERNEL32!DeviceIoControl` at `0x14000ae08`
- `KERNEL32!DeviceIoControl` at `0x14000ae08`

## string_xrefs

- `0x14000ae14`: `DeviceIoControl - IOCTL_SPACEPORT_DELETE_POOL`
- `0x14000aeb5`: `SuDeletePool`
- `0x14000aeda`: `SuDeletePool`

## pseudocode

```c
__int64 __fastcall SuDeletePool(
        struct _SU_POOL_OBJECT *a1,
        int (__high *a2)(enum _SU_OPERATION, struct _LIST_ENTRY *, void *, void *, void *, void *),
        void *a3)
{
  struct _GUID *v4; // r14
  unsigned int v5; // ebx
  const char *v6; // rdi
  HLOCAL *v7; // rax
  DWORD LastError; // esi
  int v9; // ecx
  int v10; // r8d
  int v11; // r9d
  HLOCAL v12; // rcx
  __int64 v13; // rax
  HLOCAL hMem[2]; // [rsp+40h] [rbp-30h] BYREF
  LARGE_INTEGER PerformanceCount; // [rsp+50h] [rbp-20h] BYREF
  LARGE_INTEGER v17; // [rsp+58h] [rbp-18h] BYREF
  __int64 v18; // [rsp+60h] [rbp-10h]
  DWORD BytesReturned; // [rsp+A0h] [rbp+30h] BYREF
  int v20; // [rsp+A4h] [rbp+34h]

  v20 = HIDWORD(a3);
  BytesReturned = 0;
  SI_TIMER::SI_TIMER((SI_TIMER *)&PerformanceCount);
  QueryPerformanceCounter(&PerformanceCount);
  v4 = (struct _GUID *)((char *)a1 + 40);
  hMem[1] = hMem;
  hMem[0] = hMem;
  v5 = SiBuildPoolRemovalDriveList(v4, (struct _LIST_ENTRY *)hMem);
  if ( !v5 )
  {
    v6 = "SiBuildPoolRemovalDriveList";
LABEL_10:
    LastError = GetLastError();
    goto LABEL_11;
  }
  v5 = DeviceIoControl(Spaceport, 0xE7C014u, v4, 0x10u, 0, 0, &BytesReturned, 0);
  if ( !v5 )
  {
    v6 = "DeviceIoControl - IOCTL_SPACEPORT_DELETE_POOL";
    goto LABEL_10;
  }
  v7 = (HLOCAL *)hMem[0];
  LastError = 0;
  v6 = 0;
  while ( v7 != hMem )
  {
    *(GUID *)(v7 + 5) = GUID_NULL;
    *((GUID *)v7 + 5) = GUID_NULL;
    v7 = (HLOCAL *)*v7;
  }
  v5 = SiPerformParallelOperation(2, (struct _LIST_ENTRY *)hMem, 0, 0, 0);
  if ( !v5 )
  {
    v6 = "Callback - SuOperationUnprepareDrives";
    goto LABEL_10;
  }
LABEL_11:
  QueryPerformanceCounter(&v17);
  if ( v5 )
  {
    if ( (Microsoft_Windows_StorageSpaces_ApiEnableBits & 2) != 0 )
      McTemplateK0zsjx_EventWriteTransfer(
        v17.LowPart - PerformanceCount.LowPart,
        (unsigned int)DeletePoolSucceeded,
        v10,
        v11,
        (__int64)"SuDeletePool",
        (__int64)v4,
        1000000 * (v17.QuadPart - PerformanceCount.QuadPart) / v18);
  }
  else if ( (Microsoft_Windows_StorageSpaces_ApiEnableBits & 1) != 0 )
  {
    McTemplateK0zsjsq_EventWriteTransfer(
      v9,
      (unsigned int)DeletePoolFailed,
      v10,
      v11,
      (__int64)"SuDeletePool",
      (__int64)v4,
      (__int64)v6,
      LastError);
  }
  while ( 1 )
  {
    v12 = hMem[0];
    if ( hMem[0] == hMem )
      break;
    if ( *((HLOCAL **)hMem[0] + 1) != hMem
      || (v13 = *(_QWORD *)hMem[0], *(HLOCAL *)(*(_QWORD *)hMem[0] + 8LL) != hMem[0]) )
    {
      __fastfail(3u);
    }
    hMem[0] = *(HLOCAL *)hMem[0];
    *(_QWORD *)(v13 + 8) = hMem;
    LocalFree(v12);
  }
  if ( !v5 )
    SetLastError(LastError);
  return v5;
}

```

## disassembly

```asm
0x14000ad60  mov     [rsp-18h+arg_0], rbx
0x14000ad65  mov     [rsp-18h+arg_8], rsi
0x14000ad6a  mov     qword ptr [rsp-18h+BytesReturned], r8
0x14000ad6f  push    rbp
0x14000ad70  push    rdi
0x14000ad71  push    r14
0x14000ad73  mov     rbp, rsp
0x14000ad76  sub     rsp, 70h
0x14000ad7a  mov     r14, rcx
0x14000ad7d  mov     [rbp+BytesReturned], 0
0x14000ad84  xorps   xmm0, xmm0
0x14000ad87  lea     rcx, [rbp+PerformanceCount]; this
0x14000ad8b  movups  xmmword ptr [rbp+hMem], xmm0
0x14000ad8f  call    ??0SI_TIMER@@QEAA@XZ; SI_TIMER::SI_TIMER(void)
0x14000ad94  lea     rcx, [rbp+PerformanceCount]; lpPerformanceCount
0x14000ad98  call    cs:__imp_QueryPerformanceCounter
0x14000ad9e  lea     rax, [rbp+hMem]
0x14000ada2  add     r14, 28h ; '('
0x14000ada6  mov     [rbp+hMem+8], rax
0x14000adaa  lea     rdx, [rbp+hMem]; struct _LIST_ENTRY *
0x14000adae  lea     rax, [rbp+hMem]
0x14000adb2  mov     rcx, r14; struct _GUID *
0x14000adb5  mov     [rbp+hMem], rax
0x14000adb9  call    ?SiBuildPoolRemovalDriveList@@YAHPEAU_GUID@@PEAU_LIST_ENTRY@@@Z; SiBuildPoolRemovalDriveList(_GUID *,_LIST_ENTRY *)
0x14000adbe  mov     ebx, eax
0x14000adc0  test    eax, eax
0x14000adc2  jnz     short loc_14000ADD0
0x14000adc4  lea     rdi, aSibuildpoolrem; "SiBuildPoolRemovalDriveList"
0x14000adcb  jmp     loc_14000AE75
0x14000add0  mov     rcx, cs:?Spaceport@@3PEAXEA; hDevice
0x14000add7  lea     rax, [rbp+BytesReturned]
0x14000addb  mov     [rsp+70h+lpOverlapped], 0; lpOverlapped
0x14000ade4  mov     r9d, 10h; nInBufferSize
0x14000adea  mov     [rsp+70h+lpBytesReturned], rax; lpBytesReturned
0x14000adef  mov     r8, r14; lpInBuffer
0x14000adf2  mov     [rsp+70h+nOutBufferSize], 0; nOutBufferSize
0x14000adfa  mov     edx, 0E7C014h; dwIoControlCode
0x14000adff  mov     [rsp+70h+lpOutBuffer], 0; lpOutBuffer
0x14000ae08  call    cs:__imp_DeviceIoControl
0x14000ae0e  mov     ebx, eax
0x14000ae10  test    eax, eax
0x14000ae12  jnz     short loc_14000AE1D
0x14000ae14  lea     rdi, aDeviceiocontro_3; "DeviceIoControl - IOCTL_SPACEPORT_DELET"...
0x14000ae1b  jmp     short loc_14000AE75
0x14000ae1d  mov     rax, [rbp+hMem]
0x14000ae21  xor     esi, esi
0x14000ae23  xor     edi, edi
0x14000ae25  jmp     short loc_14000AE42
0x14000ae27  movups  xmm0, xmmword ptr cs:GUID_NULL.Data1
0x14000ae2e  movdqu  xmmword ptr [rax+28h], xmm0
0x14000ae33  movups  xmm1, xmmword ptr cs:GUID_NULL.Data1
0x14000ae3a  movdqu  xmmword ptr [rax+50h], xmm1
0x14000ae3f  mov     rax, [rax]
0x14000ae42  lea     rcx, [rbp+hMem]
0x14000ae46  cmp     rax, rcx
0x14000ae49  jnz     short loc_14000AE27
0x14000ae4b  xor     r9d, r9d
0x14000ae4e  mov     qword ptr [rsp+70h+nOutBufferSize], rsi
0x14000ae53  xor     r8d, r8d
0x14000ae56  mov     [rsp+70h+lpOutBuffer], rsi
0x14000ae5b  lea     rdx, [rbp+hMem]
0x14000ae5f  lea     ecx, [r9+2]
0x14000ae63  call    ?SiPerformParallelOperation@@YAHW4_SU_OPERATION@@PEAU_LIST_ENTRY@@PEAX222@Z; SiPerformParallelOperation(_SU_OPERATION,_LIST_ENTRY *,void *,void *,void *,void *)
0x14000ae68  mov     ebx, eax
0x14000ae6a  test    eax, eax
0x14000ae6c  jnz     short loc_14000AE7D
0x14000ae6e  lea     rdi, aCallbackSuoper_0; "Callback - SuOperationUnprepareDrives"
0x14000ae75  call    cs:__imp_GetLastError
0x14000ae7b  mov     esi, eax
0x14000ae7d  lea     rcx, [rbp+var_18]; lpPerformanceCount
0x14000ae81  call    cs:__imp_QueryPerformanceCounter
0x14000ae87  test    ebx, ebx
0x14000ae89  jz      short loc_14000AECD
0x14000ae8b  test    cs:Microsoft_Windows_StorageSpaces_ApiEnableBits, 2
0x14000ae92  jz      short loc_14000AEFC
0x14000ae94  mov     rcx, qword ptr [rbp+var_18]
0x14000ae98  sub     rcx, qword ptr [rbp+PerformanceCount]
0x14000ae9c  imul    rax, rcx, 0F4240h
0x14000aea3  cqo
0x14000aea5  idiv    [rbp+var_10]
0x14000aea9  lea     rdx, DeletePoolSucceeded
0x14000aeb0  mov     [rsp+70h+lpBytesReturned], rax
0x14000aeb5  lea     rax, aSudeletepool; "SuDeletePool"
0x14000aebc  mov     qword ptr [rsp+70h+nOutBufferSize], r14
0x14000aec1  mov     [rsp+70h+lpOutBuffer], rax
0x14000aec6  call    McTemplateK0zsjx_EventWriteTransfer
0x14000aecb  jmp     short loc_14000AEFC
0x14000aecd  test    cs:Microsoft_Windows_StorageSpaces_ApiEnableBits, 1
0x14000aed4  jz      short loc_14000AEFC
0x14000aed6  mov     dword ptr [rsp+70h+lpOverlapped], esi
0x14000aeda  lea     rax, aSudeletepool; "SuDeletePool"
0x14000aee1  mov     [rsp+70h+lpBytesReturned], rdi
0x14000aee6  lea     rdx, DeletePoolFailed
0x14000aeed  mov     qword ptr [rsp+70h+nOutBufferSize], r14
0x14000aef2  mov     [rsp+70h+lpOutBuffer], rax
0x14000aef7  call    McTemplateK0zsjsq_EventWriteTransfer
0x14000aefc  mov     rcx, [rbp+hMem]; hMem
0x14000af00  lea     rax, [rbp+hMem]
0x14000af04  cmp     rcx, rax
0x14000af07  jz      short loc_14000AF37
0x14000af09  lea     rax, [rbp+hMem]
0x14000af0d  cmp     [rcx+8], rax
0x14000af11  jnz     short loc_14000AF30
0x14000af13  mov     rax, [rcx]
0x14000af16  cmp     [rax+8], rcx
0x14000af1a  jnz     short loc_14000AF30
0x14000af1c  lea     rdx, [rbp+hMem]
0x14000af20  mov     [rbp+hMem], rax
0x14000af24  mov     [rax+8], rdx
0x14000af28  call    cs:__imp_LocalFree
0x14000af2e  jmp     short loc_14000AEFC
0x14000af30  mov     ecx, 3
0x14000af35  int     29h; Win8: RtlFailFast(ecx)
0x14000af37  test    ebx, ebx
0x14000af39  jnz     short loc_14000AF43
0x14000af3b  mov     ecx, esi; dwErrCode
0x14000af3d  call    cs:__imp_SetLastError
0x14000af43  lea     r11, [rsp+70h+var_s0]
0x14000af48  mov     eax, ebx
0x14000af4a  mov     rbx, [r11+20h]
0x14000af4e  mov     rsi, [r11+28h]
0x14000af52  mov     rsp, r11
0x14000af55  pop     r14
0x14000af57  pop     rdi
0x14000af58  pop     rbp
0x14000af59  retn
```
