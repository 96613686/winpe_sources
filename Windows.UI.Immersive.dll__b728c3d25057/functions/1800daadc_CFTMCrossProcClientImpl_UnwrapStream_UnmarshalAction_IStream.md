# CFTMCrossProcClientImpl::_UnwrapStream(UnmarshalAction,IStream *)

- ea: `0x1800daadc`
- end: `0x1800dac9d`
- name: `?_UnwrapStream@CFTMCrossProcClientImpl@@AEAAJW4UnmarshalAction@@PEAUIStream@@@Z`
- size: `449`
- prototype: `int __high(enum UnmarshalAction, struct IStream *)`
- caller_count: `2`
- callee_count: `9`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x1800da920`
- `0x1800da940`

## callees

- `0x180006538`
- `0x180013244`
- `0x180013660`
- `0x180028ca0`
- `0x18002be34`
- `0x180046efc`
- `0x18006eb10`
- `0x1800daadc`
- `0x1800e5010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800dac75`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800dac75`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800dac2b`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800dac2b`
- `api-ms-win-shcore-stream-l1-1-0!IStream_Read` at `0x1800dabbd`
- `api-ms-win-shcore-stream-l1-1-0!IStream_Read` at `0x1800dac18`
- `api-ms-win-shcore-stream-l1-1-0!IStream_Read` at `0x1800dabbd`
- `api-ms-win-shcore-stream-l1-1-0!IStream_Read` at `0x1800dac18`
- `api-ms-win-shcore-stream-l1-1-0!SHCreateMemStream` at `0x1800dac37`
- `api-ms-win-shcore-stream-l1-1-0!SHCreateMemStream` at `0x1800dac37`
- `api-ms-win-core-com-l1-1-0!CoUnmarshalInterface` at `0x1800dab25`
- `api-ms-win-core-com-l1-1-0!CoUnmarshalInterface` at `0x1800dab25`
- `api-ms-win-core-com-l1-1-0!CoReleaseMarshalData` at `0x1800dab9d`
- `api-ms-win-core-com-l1-1-0!CoReleaseMarshalData` at `0x1800dab9d`
- `api-ms-win-core-com-l1-1-1!RoGetAgileReference` at `0x1800dab65`
- `api-ms-win-core-com-l1-1-1!RoGetAgileReference` at `0x1800dab65`

## pseudocode

```c
__int64 __fastcall CFTMCrossProcClientImpl::_UnwrapStream(__int64 a1, unsigned int a2, IStream *a3)
{
  LPVOID v6; // rdi
  unsigned __int64 *v7; // rax
  unsigned __int64 *v8; // rbx
  UINT *v9; // r14
  unsigned __int64 v10; // rcx
  BYTE *v11; // rbx
  void *v12; // rcx
  unsigned int v13; // r10d
  int v14; // eax
  IStream *v15; // rax
  unsigned __int64 v17; // [rsp+20h] [rbp-10h] BYREF
  __int64 v18; // [rsp+28h] [rbp-8h] BYREF
  LPVOID ppv; // [rsp+78h] [rbp+48h] BYREF

  if ( a2 )
  {
    LODWORD(v6) = CoReleaseMarshalData(a3);
  }
  else
  {
    ppv = 0;
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&ppv);
    LODWORD(v6) = CoUnmarshalInterface(a3, &GUID_00000000_0000_0000_c000_000000000046, &ppv);
    if ( (int)v6 >= 0 )
    {
      v6 = ppv;
      v17 = a1 + 72;
      v7 = (unsigned __int64 *)Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::AgileRef>::operator Microsoft::WRL::AgileRef *(&v17);
      v8 = v7;
      if ( v6 )
      {
        Microsoft::WRL::ComPtr<IFrameTaskManager>::InternalRelease(v7);
        LODWORD(v6) = RoGetAgileReference(0, &GUID_00000000_0000_0000_c000_000000000046, v6, v8);
      }
      else
      {
        v17 = *v7;
        v18 = 0;
        *v7 = 0;
        Microsoft::WRL::ComPtr<IFrameTaskManager>::InternalRelease(&v17);
        Microsoft::WRL::ComPtr<IFrameTaskManager>::InternalRelease(&v18);
      }
    }
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&ppv);
  }
  if ( (int)v6 >= 0 )
  {
    v9 = (UINT *)(a1 + 32);
    LODWORD(v6) = IStream_Read(a3, (void *)(a1 + 32), 4u);
    if ( (int)v6 >= 0 )
    {
      v10 = *v9;
      v11 = 0;
      ppv = 0;
      v17 = 0;
      LODWORD(v6) = ULongLongMult(v10, 1u, &v17);
      if ( (int)v6 >= 0 )
      {
        v14 = CTCoAllocPolicy::Alloc(v12, v13, v17, &ppv);
        v11 = (BYTE *)ppv;
        LODWORD(v6) = v14;
      }
      if ( (int)v6 >= 0 )
      {
        if ( !*v9 || (LODWORD(v6) = IStream_Read(a3, v11, *v9), (int)v6 >= 0) )
        {
          EnterCriticalSection((LPCRITICAL_SECTION)(a1 + 88));
          v15 = SHCreateMemStream(v11, *v9);
          Microsoft::WRL::ComPtr<Windows::Internal::PopupWindowXAMLContentImpl>::Attach(a1 + 80, v15);
          if ( *(_QWORD *)(a1 + 80) )
            LODWORD(v6) = (*(__int64 (__fastcall **)(__int64, _QWORD))(*(_QWORD *)a1 + 96LL))(a1, a2);
          else
            LODWORD(v6) = -2147024882;
          if ( a1 != -88 )
            LeaveCriticalSection((LPCRITICAL_SECTION)(a1 + 88));
        }
      }
      CCoTaskMemPtr<unsigned char>::~CCoTaskMemPtr<unsigned char>(&ppv);
    }
  }
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x1800daadc  mov     [rsp-28h+arg_0], rbx
0x1800daae1  mov     [rsp-28h+arg_8], rsi
0x1800daae6  push    rbp
0x1800daae7  push    rdi
0x1800daae8  push    r12
0x1800daaea  push    r14
0x1800daaec  push    r15
0x1800daaee  mov     rbp, rsp
0x1800daaf1  sub     rsp, 30h
0x1800daaf5  mov     rsi, r8
0x1800daaf8  mov     r12d, edx
0x1800daafb  mov     r15, rcx
0x1800daafe  test    edx, edx
0x1800dab00  jnz     loc_1800DAB9A
0x1800dab06  lea     rcx, [rbp+ppv]
0x1800dab0a  mov     [rbp+ppv], 0
0x1800dab12  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800dab17  lea     r8, [rbp+ppv]; ppv
0x1800dab1b  mov     rcx, rsi; pStm
0x1800dab1e  lea     rdx, _GUID_00000000_0000_0000_c000_000000000046; riid
0x1800dab25  call    cs:__imp_CoUnmarshalInterface
0x1800dab2b  mov     edi, eax
0x1800dab2d  test    eax, eax
0x1800dab2f  js      short loc_1800DAB8F
0x1800dab31  mov     rdi, [rbp+ppv]
0x1800dab35  lea     rax, [r15+48h]
0x1800dab39  lea     rcx, [rbp+var_10]
0x1800dab3d  mov     [rbp+var_10], rax
0x1800dab41  call    ??B?$ComPtrRef@VAgileRef@WRL@Microsoft@@@Details@WRL@Microsoft@@QEAAPEAVAgileRef@23@XZ; Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::AgileRef>::operator Microsoft::WRL::AgileRef *(void)
0x1800dab46  mov     rbx, rax
0x1800dab49  test    rdi, rdi
0x1800dab4c  jz      short loc_1800DAB6F
0x1800dab4e  mov     rcx, rax
0x1800dab51  call    ?InternalRelease@?$ComPtr@UIFrameTaskManager@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IFrameTaskManager>::InternalRelease(void)
0x1800dab56  mov     r9, rbx
0x1800dab59  lea     rdx, _GUID_00000000_0000_0000_c000_000000000046
0x1800dab60  mov     r8, rdi
0x1800dab63  xor     ecx, ecx
0x1800dab65  call    cs:__imp_RoGetAgileReference
0x1800dab6b  mov     edi, eax
0x1800dab6d  jmp     short loc_1800DAB8F
0x1800dab6f  mov     rax, [rax]
0x1800dab72  lea     rcx, [rbp+var_10]
0x1800dab76  mov     [rbp+var_10], rax
0x1800dab7a  mov     [rbp+var_8], rdi
0x1800dab7e  mov     [rbx], rdi
0x1800dab81  call    ?InternalRelease@?$ComPtr@UIFrameTaskManager@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IFrameTaskManager>::InternalRelease(void)
0x1800dab86  lea     rcx, [rbp+var_8]
0x1800dab8a  call    ?InternalRelease@?$ComPtr@UIFrameTaskManager@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IFrameTaskManager>::InternalRelease(void)
0x1800dab8f  lea     rcx, [rbp+ppv]
0x1800dab93  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800dab98  jmp     short loc_1800DABA5
0x1800dab9a  mov     rcx, rsi; pStm
0x1800dab9d  call    cs:__imp_CoReleaseMarshalData
0x1800daba3  mov     edi, eax
0x1800daba5  test    edi, edi
0x1800daba7  js      loc_1800DAC84
0x1800dabad  lea     r14, [r15+20h]
0x1800dabb1  mov     r8d, 4; cb
0x1800dabb7  mov     rdx, r14; pv
0x1800dabba  mov     rcx, rsi; pstm
0x1800dabbd  call    cs:__imp_IStream_Read
0x1800dabc3  mov     edi, eax
0x1800dabc5  test    eax, eax
0x1800dabc7  js      loc_1800DAC84
0x1800dabcd  mov     ecx, [r14]; unsigned __int64
0x1800dabd0  lea     r8, [rbp+var_10]; unsigned __int64 *
0x1800dabd4  xor     ebx, ebx
0x1800dabd6  mov     [rbp+ppv], rbx
0x1800dabda  mov     [rbp+var_10], rbx
0x1800dabde  lea     r10d, [rbx+1]
0x1800dabe2  mov     edx, r10d; unsigned __int64
0x1800dabe5  call    ?ULongLongMult@@YAJ_K0PEA_K@Z; ULongLongMult(unsigned __int64,unsigned __int64,unsigned __int64 *)
0x1800dabea  mov     edi, eax
0x1800dabec  test    eax, eax
0x1800dabee  js      short loc_1800DAC06
0x1800dabf0  mov     r8, [rbp+var_10]; unsigned __int64
0x1800dabf4  lea     r9, [rbp+ppv]; void **
0x1800dabf8  mov     edx, r10d; unsigned int
0x1800dabfb  call    ?Alloc@CTCoAllocPolicy@@SAJPEAXK_KPEAPEAX@Z; CTCoAllocPolicy::Alloc(void *,ulong,unsigned __int64,void * *)
0x1800dac00  mov     rbx, [rbp+ppv]
0x1800dac04  mov     edi, eax
0x1800dac06  test    edi, edi
0x1800dac08  js      short loc_1800DAC7B
0x1800dac0a  mov     r8d, [r14]; cb
0x1800dac0d  test    r8d, r8d
0x1800dac10  jz      short loc_1800DAC24
0x1800dac12  mov     rdx, rbx; pv
0x1800dac15  mov     rcx, rsi; pstm
0x1800dac18  call    cs:__imp_IStream_Read
0x1800dac1e  mov     edi, eax
0x1800dac20  test    eax, eax
0x1800dac22  js      short loc_1800DAC7B
0x1800dac24  lea     rsi, [r15+58h]
0x1800dac28  mov     rcx, rsi; lpCriticalSection
0x1800dac2b  call    cs:__imp_EnterCriticalSection
0x1800dac31  mov     edx, [r14]; cbInit
0x1800dac34  mov     rcx, rbx; pInit
0x1800dac37  call    cs:__imp_SHCreateMemStream
0x1800dac3d  mov     rdx, rax
0x1800dac40  lea     rcx, [r15+50h]
0x1800dac44  call    ?Attach@?$ComPtr@VPopupWindowXAMLContentImpl@Internal@Windows@@@WRL@Microsoft@@QEAAXPEAVPopupWindowXAMLContentImpl@Internal@Windows@@@Z; Microsoft::WRL::ComPtr<Windows::Internal::PopupWindowXAMLContentImpl>::Attach(Windows::Internal::PopupWindowXAMLContentImpl *)
0x1800dac49  mov     r8, [r15+50h]
0x1800dac4d  test    r8, r8
0x1800dac50  jnz     short loc_1800DAC59
0x1800dac52  mov     edi, 8007000Eh
0x1800dac57  jmp     short loc_1800DAC6D
0x1800dac59  mov     rax, [r15]
0x1800dac5c  mov     edx, r12d
0x1800dac5f  mov     rcx, r15
0x1800dac62  mov     rax, [rax+60h]
0x1800dac66  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800dac6b  mov     edi, eax
0x1800dac6d  test    rsi, rsi
0x1800dac70  jz      short loc_1800DAC7B
0x1800dac72  mov     rcx, rsi; lpCriticalSection
0x1800dac75  call    cs:__imp_LeaveCriticalSection
0x1800dac7b  lea     rcx, [rbp+ppv]
0x1800dac7f  call    ??1?$CCoTaskMemPtr@E@@QEAA@XZ; CCoTaskMemPtr<uchar>::~CCoTaskMemPtr<uchar>(void)
0x1800dac84  mov     rbx, [rsp+30h+arg_0]
0x1800dac89  mov     eax, edi
0x1800dac8b  mov     rsi, [rsp+30h+arg_8]
0x1800dac90  add     rsp, 30h
0x1800dac94  pop     r15
0x1800dac96  pop     r14
0x1800dac98  pop     r12
0x1800dac9a  pop     rdi
0x1800dac9b  pop     rbp
0x1800dac9c  retn
```
