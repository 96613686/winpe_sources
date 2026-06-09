# GipRawDeviceIO::SendRawDeviceOutput(unsigned __int64,IGameInputRawDeviceReport *)

- ea: `0x18000ac9c`
- end: `0x18000afc0`
- name: `?SendRawDeviceOutput@GipRawDeviceIO@@SAJ_KPEAUIGameInputRawDeviceReport@@@Z`
- size: `804`
- prototype: `__int64 __fastcall(unsigned __int64, struct IGameInputRawDeviceReport *)`
- caller_count: `1`
- callee_count: `4`
- tags: `file_ops, loader_planting`

## callers

- `0x18000ac20`

## callees

- `0x180001304`
- `0x18000ac9c`
- `0x18000c11c`
- `0x18004d010`

## import_xrefs

- `ntdll!RtlAllocateHeap` at `0x18000adcf`
- `ntdll!RtlAllocateHeap` at `0x18000adcf`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x18000aee3`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x18000aee3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000aef7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000aef7`

## pseudocode

```c
__int64 __fastcall GipRawDeviceIO::SendRawDeviceOutput(__int64 a1, struct IGameInputRawDeviceReport *a2)
{
  __int64 (__fastcall **v5)(struct IGameInputRawDeviceReport *, GUID *, __int64 *); // rax
  __int64 v6; // rdx
  int v7; // edi
  int v8; // r8d
  int v9; // r9d
  unsigned int v10; // r14d
  _QWORD *Heap; // rax
  int v12; // r8d
  int v13; // r9d
  _BYTE *v14; // rdi
  signed int LastError; // ebx
  const struct std::nothrow_t *v16; // rdx
  const struct std::nothrow_t *v17; // rdx
  int v18; // r8d
  int v19; // r9d
  DWORD NumberOfBytesWritten; // [rsp+40h] [rbp-20h] BYREF
  __int64 v21; // [rsp+48h] [rbp-18h] BYREF
  _QWORD v22[2]; // [rsp+50h] [rbp-10h] BYREF
  int v23; // [rsp+A0h] [rbp+40h] BYREF
  int v24; // [rsp+A8h] [rbp+48h] BYREF

  if ( !byte_180069915 )
    return 2147500033LL;
  if ( GipRawDeviceIO::s_gipClientHandle == (HANDLE)-1LL )
    return 2147500037LL;
  if ( *(_DWORD *)(*(__int64 (__fastcall **)(struct IGameInputRawDeviceReport *))(*(_QWORD *)a2 + 32LL))(a2) != 1 )
    return 2147942487LL;
  v5 = *(__int64 (__fastcall ***)(struct IGameInputRawDeviceReport *, GUID *, __int64 *))a2;
  v21 = 0;
  v7 = (*v5)(a2, &GUID_6f5e2bf7_001b_434d_aa26_cbfdafdf5605, &v21);
  if ( v7 < 0 )
  {
    if ( (unsigned int)dword_180069000 > 2 )
    {
      v6 = qword_180069018;
      if ( (qword_180069010 & 1) != 0 && (qword_180069018 & 1) == qword_180069018 )
      {
        v23 = v7;
        v22[0] = "onecore\\xbox\\gameinput\\client\\GipRawDeviceIO.cpp";
        v24 = 37;
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_GameInputEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
          qword_180069010,
          (unsigned int)&unk_180059CE8,
          v8,
          v9,
          (__int64)v22,
          (__int64)&v24,
          (__int64)&v23);
      }
    }
    if ( v21 )
      (*(void (__fastcall **)(__int64, __int64))(*(_QWORD *)v21 + 16LL))(v21, v6);
    return (unsigned int)v7;
  }
  v10 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v21 + 96LL))(v21);
  Heap = RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 0, v10 + 20);
  v14 = Heap;
  if ( !Heap )
  {
    LastError = -2147024882;
    if ( (unsigned int)dword_180069000 > 2 && (qword_180069010 & 1) != 0 && (qword_180069018 & 1) == qword_180069018 )
    {
      v23 = -2147024882;
      v22[0] = "onecore\\xbox\\gameinput\\client\\GipRawDeviceIO.cpp";
      v24 = 43;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_GameInputEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
        qword_180069018,
        (unsigned int)&byte_1800598A7,
        v12,
        v13,
        (__int64)v22,
        (__int64)&v24,
        (__int64)&v23);
    }
LABEL_20:
    if ( v21 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v21 + 16LL))(v21);
    return (unsigned int)LastError;
  }
  Heap[1] = 0;
  *((_DWORD *)Heap + 4) = 0;
  *Heap = a1;
  *((_BYTE *)Heap + 8) = *(_BYTE *)((*(__int64 (__fastcall **)(struct IGameInputRawDeviceReport *))(*(_QWORD *)a2 + 32LL))(a2)
                                  + 4);
  v14[9] = BYTE6(a1);
  *((_WORD *)v14 + 5) = 0;
  *((_DWORD *)v14 + 3) = v10;
  *((_DWORD *)v14 + 4) = 0;
  (*(void (__fastcall **)(struct IGameInputRawDeviceReport *, _QWORD, _BYTE *))(*(_QWORD *)a2 + 48LL))(
    a2,
    v10,
    v14 + 20);
  NumberOfBytesWritten = 0;
  if ( !WriteFile(GipRawDeviceIO::s_gipClientHandle, v14, v10 + 20, &NumberOfBytesWritten, 0) )
  {
    LastError = GetLastError();
    if ( (unsigned int)dword_180069000 > 2 && (qword_180069010 & 1) != 0 && (qword_180069018 & 1) == qword_180069018 )
    {
      v23 = LastError;
      v22[0] = "onecore\\xbox\\gameinput\\client\\GipRawDeviceIO.cpp";
      v24 = 63;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_GameInputEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
        qword_180069018,
        (unsigned int)byte_180059A33,
        v18,
        v19,
        (__int64)v22,
        (__int64)&v24,
        (__int64)&v23);
    }
    if ( LastError )
    {
      if ( LastError > 0 )
        LastError = (unsigned __int16)LastError | 0x80070000;
    }
    else
    {
      LastError = -2147418113;
    }
    operator delete(v14, v17);
    goto LABEL_20;
  }
  operator delete(v14, v16);
  if ( v21 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v21 + 16LL))(v21);
  return 0;
}

```

## disassembly

```asm
0x18000ac9c  mov     [rsp-28h+arg_0], rbx
0x18000aca1  push    rbp
0x18000aca2  push    rsi
0x18000aca3  push    rdi
0x18000aca4  push    r14
0x18000aca6  push    r15
0x18000aca8  mov     rbp, rsp
0x18000acab  sub     rsp, 60h
0x18000acaf  cmp     cs:byte_180069915, 0
0x18000acb6  mov     rbx, rdx
0x18000acb9  mov     rsi, rcx
0x18000acbc  jnz     short loc_18000ACC8
0x18000acbe  mov     eax, 80004001h
0x18000acc3  jmp     loc_18000AFAB
0x18000acc8  cmp     cs:?s_gipClientHandle@GipRawDeviceIO@@0PEAXEA, 0FFFFFFFFFFFFFFFFh; void * GipRawDeviceIO::s_gipClientHandle
0x18000acd0  jnz     short loc_18000ACDC
0x18000acd2  mov     eax, 80004005h
0x18000acd7  jmp     loc_18000AFAB
0x18000acdc  mov     rax, [rdx]
0x18000acdf  mov     rcx, rbx
0x18000ace2  mov     rax, [rax+20h]
0x18000ace6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000aceb  cmp     dword ptr [rax], 1
0x18000acee  jz      short loc_18000ACFA
0x18000acf0  mov     eax, 80070057h
0x18000acf5  jmp     loc_18000AFAB
0x18000acfa  mov     rax, [rbx]
0x18000acfd  lea     r8, [rbp+var_18]
0x18000ad01  lea     rdx, _GUID_6f5e2bf7_001b_434d_aa26_cbfdafdf5605
0x18000ad08  mov     [rbp+var_18], 0
0x18000ad10  mov     rcx, rbx
0x18000ad13  mov     rax, [rax]
0x18000ad16  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ad1b  mov     edi, eax
0x18000ad1d  test    eax, eax
0x18000ad1f  jns     loc_18000ADA6
0x18000ad25  mov     ecx, cs:dword_180069000
0x18000ad2b  cmp     ecx, 2
0x18000ad2e  jbe     short loc_18000AD8A
0x18000ad30  mov     rdx, cs:qword_180069018
0x18000ad37  mov     rcx, cs:qword_180069010
0x18000ad3e  test    cl, 1
0x18000ad41  jz      short loc_18000AD8A
0x18000ad43  mov     rax, rdx
0x18000ad46  and     eax, 1
0x18000ad49  cmp     rax, rdx
0x18000ad4c  jnz     short loc_18000AD8A
0x18000ad4e  lea     rax, aOnecoreXboxGam_8; "onecore\\xbox\\gameinput\\client\\GipRa"...
0x18000ad55  mov     [rbp+arg_10], edi
0x18000ad58  mov     [rbp+var_10], rax
0x18000ad5c  lea     rdx, unk_180059CE8
0x18000ad63  lea     rax, [rbp+arg_10]
0x18000ad67  mov     [rbp+arg_18], 25h ; '%'
0x18000ad6e  mov     [rsp+60h+var_30], rax
0x18000ad73  lea     rax, [rbp+arg_18]
0x18000ad77  mov     [rsp+60h+var_38], rax
0x18000ad7c  lea     rax, [rbp+var_10]
0x18000ad80  mov     [rsp+60h+lpOverlapped], rax
0x18000ad85  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_GameInputEventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_GameInputEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x18000ad8a  mov     rcx, [rbp+var_18]
0x18000ad8e  test    rcx, rcx
0x18000ad91  jz      short loc_18000AD9F
0x18000ad93  mov     rax, [rcx]
0x18000ad96  mov     rax, [rax+10h]
0x18000ad9a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ad9f  mov     eax, edi
0x18000ada1  jmp     loc_18000AFAB
0x18000ada6  mov     rcx, [rbp+var_18]
0x18000adaa  mov     rax, [rcx]
0x18000adad  mov     rax, [rax+60h]
0x18000adb1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000adb6  mov     rcx, gs:60h
0x18000adbf  xor     edx, edx; Flags
0x18000adc1  mov     r14, rax
0x18000adc4  lea     r15d, [rax+14h]
0x18000adc8  mov     rcx, [rcx+30h]; HeapHandle
0x18000adcc  mov     r8d, r15d; Size
0x18000adcf  call    cs:__imp_RtlAllocateHeap
0x18000add6  nop     dword ptr [rax+rax+00h]
0x18000addb  mov     rdi, rax
0x18000adde  test    rax, rax
0x18000ade1  jnz     loc_18000AE6C
0x18000ade7  mov     eax, cs:dword_180069000
0x18000aded  mov     ebx, 8007000Eh
0x18000adf2  cmp     eax, 2
0x18000adf5  jbe     short loc_18000AE50
0x18000adf7  mov     rcx, cs:qword_180069018
0x18000adfe  mov     rax, cs:qword_180069010
0x18000ae05  test    al, 1
0x18000ae07  jz      short loc_18000AE50
0x18000ae09  mov     rax, rcx
0x18000ae0c  and     eax, 1
0x18000ae0f  cmp     rax, rcx
0x18000ae12  jnz     short loc_18000AE50
0x18000ae14  lea     rax, aOnecoreXboxGam_8; "onecore\\xbox\\gameinput\\client\\GipRa"...
0x18000ae1b  mov     [rbp+arg_10], ebx
0x18000ae1e  mov     [rbp+var_10], rax
0x18000ae22  lea     rdx, byte_1800598A7
0x18000ae29  lea     rax, [rbp+arg_10]
0x18000ae2d  mov     [rbp+arg_18], 2Bh ; '+'
0x18000ae34  mov     [rsp+60h+var_30], rax
0x18000ae39  lea     rax, [rbp+arg_18]
0x18000ae3d  mov     [rsp+60h+var_38], rax
0x18000ae42  lea     rax, [rbp+var_10]
0x18000ae46  mov     [rsp+60h+lpOverlapped], rax
0x18000ae4b  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_GameInputEventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_GameInputEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x18000ae50  mov     rcx, [rbp+var_18]
0x18000ae54  test    rcx, rcx
0x18000ae57  jz      short loc_18000AE65
0x18000ae59  mov     rdx, [rcx]
0x18000ae5c  mov     rax, [rdx+10h]
0x18000ae60  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ae65  mov     eax, ebx
0x18000ae67  jmp     loc_18000AFAB
0x18000ae6c  mov     qword ptr [rax+8], 0
0x18000ae74  mov     rcx, rbx
0x18000ae77  mov     dword ptr [rax+10h], 0
0x18000ae7e  mov     [rax], rsi
0x18000ae81  mov     rax, [rbx]
0x18000ae84  mov     rax, [rax+20h]
0x18000ae88  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ae8d  shr     rsi, 30h
0x18000ae91  lea     r8, [rdi+14h]
0x18000ae95  mov     edx, r14d
0x18000ae98  mov     cl, [rax+4]
0x18000ae9b  mov     [rdi+8], cl
0x18000ae9e  mov     rcx, rbx
0x18000aea1  mov     [rdi+9], sil
0x18000aea5  mov     word ptr [rdi+0Ah], 0
0x18000aeab  mov     [rdi+0Ch], r14d
0x18000aeaf  mov     dword ptr [rdi+10h], 0
0x18000aeb6  mov     rax, [rbx]
0x18000aeb9  mov     rax, [rax+30h]
0x18000aebd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000aec2  mov     rcx, cs:?s_gipClientHandle@GipRawDeviceIO@@0PEAXEA; hFile
0x18000aec9  lea     r9, [rbp+NumberOfBytesWritten]; lpNumberOfBytesWritten
0x18000aecd  mov     r8d, r15d; nNumberOfBytesToWrite
0x18000aed0  mov     [rbp+NumberOfBytesWritten], 0
0x18000aed7  mov     rdx, rdi; lpBuffer
0x18000aeda  mov     [rsp+60h+lpOverlapped], 0; lpOverlapped
0x18000aee3  call    cs:__imp_WriteFile
0x18000aeea  nop     dword ptr [rax+rax+00h]
0x18000aeef  test    eax, eax
0x18000aef1  jnz     loc_18000AF8C
0x18000aef7  call    cs:__imp_GetLastError
0x18000aefe  nop     dword ptr [rax+rax+00h]
0x18000af03  mov     ebx, eax
0x18000af05  mov     eax, cs:dword_180069000
0x18000af0b  cmp     eax, 2
0x18000af0e  jbe     short loc_18000AF69
0x18000af10  mov     rcx, cs:qword_180069018
0x18000af17  mov     rax, cs:qword_180069010
0x18000af1e  test    al, 1
0x18000af20  jz      short loc_18000AF69
0x18000af22  mov     rax, rcx
0x18000af25  and     eax, 1
0x18000af28  cmp     rax, rcx
0x18000af2b  jnz     short loc_18000AF69
0x18000af2d  lea     rax, aOnecoreXboxGam_8; "onecore\\xbox\\gameinput\\client\\GipRa"...
0x18000af34  mov     [rbp+arg_10], ebx
0x18000af37  mov     [rbp+var_10], rax
0x18000af3b  lea     rdx, byte_180059A33
0x18000af42  lea     rax, [rbp+arg_10]
0x18000af46  mov     [rbp+arg_18], 3Fh ; '?'
0x18000af4d  mov     [rsp+60h+var_30], rax
0x18000af52  lea     rax, [rbp+arg_18]
0x18000af56  mov     [rsp+60h+var_38], rax
0x18000af5b  lea     rax, [rbp+var_10]
0x18000af5f  mov     [rsp+60h+lpOverlapped], rax
0x18000af64  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_GameInputEventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_GameInputEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x18000af69  test    ebx, ebx
0x18000af6b  jnz     short loc_18000AF74
0x18000af6d  mov     ebx, 8000FFFFh
0x18000af72  jmp     short loc_18000AF7F
0x18000af74  jle     short loc_18000AF7F
0x18000af76  movzx   ebx, bx
0x18000af79  or      ebx, 80070000h
0x18000af7f  mov     rcx, rdi; P
0x18000af82  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18000af87  jmp     loc_18000AE50
0x18000af8c  mov     rcx, rdi; P
0x18000af8f  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18000af94  mov     rcx, [rbp+var_18]
0x18000af98  test    rcx, rcx
0x18000af9b  jz      short loc_18000AFA9
0x18000af9d  mov     rax, [rcx]
0x18000afa0  mov     rax, [rax+10h]
0x18000afa4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000afa9  xor     eax, eax
0x18000afab  mov     rbx, [rsp+60h+arg_0]
0x18000afb3  add     rsp, 60h
0x18000afb7  pop     r15
0x18000afb9  pop     r14
0x18000afbb  pop     rdi
0x18000afbc  pop     rsi
0x18000afbd  pop     rbp
0x18000afbe  retn
```
