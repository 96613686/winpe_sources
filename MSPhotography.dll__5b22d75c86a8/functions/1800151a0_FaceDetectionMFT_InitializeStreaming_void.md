# FaceDetectionMFT::InitializeStreaming(void)

- ea: `0x1800151a0`
- end: `0x1800153a9`
- name: `?InitializeStreaming@FaceDetectionMFT@@EEAAJXZ`
- size: `521`
- prototype: `__int64 __fastcall(FaceDetectionMFT *__hidden this)`
- caller_count: `2`
- callee_count: `6`
- tags: `service_task, broker_com_uri`

## callers

- `0x18000dc9c`
- `0x180017f8c`

## callees

- `0x18000b480`
- `0x18000b490`
- `0x18000c0f8`
- `0x18000d53c`
- `0x18000f338`
- `0x1800151a0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800151ba`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800151ca`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800151ba`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800151ca`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001538b`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180015394`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001538b`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180015394`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180015212`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180015294`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180015212`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180015294`
- `MFPlat!MFGetSystemTime` at `0x1800152c6`
- `MFPlat!MFGetSystemTime` at `0x1800152c6`

## pseudocode

```c
__int64 __fastcall FaceDetectionMFT::InitializeStreaming(FaceDetectionMFT *this)
{
  struct _RTL_CRITICAL_SECTION *v1; // rbp
  char v3; // di
  _QWORD *v4; // rsi
  __int64 unique_cotaskmem; // rax
  void *v6; // rcx
  unsigned int v7; // esi
  int v8; // ecx
  __int64 v9; // rdx
  __int64 v10; // rax
  void *v11; // rcx
  __int64 v12; // r14
  LPVOID pv; // [rsp+70h] [rbp+8h] BYREF

  v1 = (struct _RTL_CRITICAL_SECTION *)((char *)this + 424);
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 424));
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 464));
  v3 = 1;
  *((_BYTE *)this + 713) = 1;
  v4 = (_QWORD *)((char *)this + 976);
  unique_cotaskmem = wil::make_unique_cotaskmem_nothrow<unsigned char [0]>(&pv, 8);
  wistd::unique_ptr<unsigned char [0],wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>>::operator=(
    (char *)this + 976,
    unique_cotaskmem);
  v6 = pv;
  pv = 0;
  if ( v6 )
    CoTaskMemFree(v6);
  if ( !*v4 )
  {
    v7 = -2147024882;
    if ( !_MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
      goto LABEL_15;
    v9 = 209;
    goto LABEL_6;
  }
  *(_QWORD *)*v4 = 8;
  v10 = wil::make_unique_cotaskmem_nothrow<unsigned char [0]>(&pv, 24);
  wistd::unique_ptr<unsigned char [0],wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>>::operator=(
    (char *)this + 984,
    v10);
  v11 = pv;
  pv = 0;
  if ( v11 )
    CoTaskMemFree(v11);
  v12 = *((_QWORD *)this + 123);
  if ( v12 )
  {
    v7 = 0;
    *(_DWORD *)v12 = 1;
    *(_QWORD *)(v12 + 8) = MFGetSystemTime();
    if ( !*((_BYTE *)this + 624) )
    {
      *((_BYTE *)this + 712) = 1;
      *((_DWORD *)this + 253) = 3;
      *((_DWORD *)this + 255) = 3;
      *((_BYTE *)this + 561) = 0;
      *((_QWORD *)this + 92) = 0x8000000000000000uLL;
      v3 = 0;
      *((_QWORD *)this + 119) = 0x8000000000000000uLL;
      *((_DWORD *)this + 141) = 0;
      *((_WORD *)this + 444) = 0;
      *((_DWORD *)this + 252) = 2;
      *((_OWORD *)this + 51) = 0;
      *((_QWORD *)this + 93) = 0;
      *((_OWORD *)this + 52) = 0;
      *((_QWORD *)this + 94) = 0;
    }
    *((_BYTE *)this + 713) = v3;
    *((_DWORD *)this + 4370) = 0;
  }
  else
  {
    v7 = -2147024882;
    if ( _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
    {
      v9 = 210;
LABEL_6:
      WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), v9, &WPP_45b7a7f164d436fa30fa2a10d6f3fbff_Traceguids, this, v8);
    }
  }
LABEL_15:
  if ( _MFControlLevel_CTRLGUID_MF_CORE_MFTS::GetLevel() >= 0x20u )
    WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 27), 211, &WPP_45b7a7f164d436fa30fa2a10d6f3fbff_Traceguids, this, v7);
  LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 464));
  LeaveCriticalSection(v1);
  return v7;
}

```

## disassembly

```asm
0x1800151a0  push    rbx
0x1800151a2  push    rbp
0x1800151a3  push    rsi
0x1800151a4  push    rdi
0x1800151a5  push    r14
0x1800151a7  push    r15
0x1800151a9  sub     rsp, 38h
0x1800151ad  lea     rbp, [rcx+1A8h]
0x1800151b4  mov     rbx, rcx
0x1800151b7  mov     rcx, rbp; lpCriticalSection
0x1800151ba  call    cs:__imp_EnterCriticalSection
0x1800151c0  lea     r15, [rbx+1D0h]
0x1800151c7  mov     rcx, r15; lpCriticalSection
0x1800151ca  call    cs:__imp_EnterCriticalSection
0x1800151d0  mov     edi, 1
0x1800151d5  lea     rcx, [rsp+68h+pv]
0x1800151da  mov     [rbx+2C9h], dil
0x1800151e1  lea     rsi, [rbx+3D0h]
0x1800151e8  lea     r14d, [rdi+7]
0x1800151ec  mov     edx, r14d
0x1800151ef  call    ??$make_unique_cotaskmem_nothrow@$$BY0A@E@wil@@YA?AV?$unique_ptr@$$BY0A@EU?$function_deleter@P6AXPEAX@Z$1?CoTaskMemFree@@YAX0@Z@wil@@@wistd@@_K@Z; wil::make_unique_cotaskmem_nothrow<uchar [0]>(unsigned __int64)
0x1800151f4  mov     rdx, rax
0x1800151f7  mov     rcx, rsi
0x1800151fa  call    ??4?$unique_ptr@$$BY0A@EU?$function_deleter@P6AXPEAX@Z$1?CoTaskMemFree@@YAX0@Z@wil@@@wistd@@QEAAAEAV01@$$QEAV01@@Z; wistd::unique_ptr<uchar [0],wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>>::operator=(wistd::unique_ptr<uchar [0],wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>> &&)
0x1800151ff  mov     rcx, [rsp+68h+pv]; pv
0x180015204  mov     [rsp+68h+pv], 0
0x18001520d  test    rcx, rcx
0x180015210  jz      short loc_180015218
0x180015212  call    cs:__imp_CoTaskMemFree
0x180015218  mov     rax, [rsi]
0x18001521b  test    rax, rax
0x18001521e  jnz     short loc_18001525D
0x180015220  mov     ecx, 8007000Eh
0x180015225  mov     esi, ecx
0x180015227  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_PLATFORM@@SAEXZ; _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel(void)
0x18001522c  cmp     al, dil
0x18001522f  jb      loc_180015359
0x180015235  mov     edx, 0D1h
0x18001523a  mov     [rsp+68h+var_48], ecx
0x18001523e  lea     r8, WPP_45b7a7f164d436fa30fa2a10d6f3fbff_Traceguids
0x180015245  mov     rcx, cs:WPP_GLOBAL_Control
0x18001524c  mov     r9, rbx
0x18001524f  mov     rcx, [rcx+10h]
0x180015253  call    WPP_SF_qD
0x180015258  jmp     loc_180015359
0x18001525d  mov     [rax], r14
0x180015260  lea     rcx, [rsp+68h+pv]
0x180015265  mov     edx, 18h
0x18001526a  lea     r14, [rbx+3D8h]
0x180015271  call    ??$make_unique_cotaskmem_nothrow@$$BY0A@E@wil@@YA?AV?$unique_ptr@$$BY0A@EU?$function_deleter@P6AXPEAX@Z$1?CoTaskMemFree@@YAX0@Z@wil@@@wistd@@_K@Z; wil::make_unique_cotaskmem_nothrow<uchar [0]>(unsigned __int64)
0x180015276  mov     rdx, rax
0x180015279  mov     rcx, r14
0x18001527c  call    ??4?$unique_ptr@$$BY0A@EU?$function_deleter@P6AXPEAX@Z$1?CoTaskMemFree@@YAX0@Z@wil@@@wistd@@QEAAAEAV01@$$QEAV01@@Z; wistd::unique_ptr<uchar [0],wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>>::operator=(wistd::unique_ptr<uchar [0],wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>> &&)
0x180015281  mov     rcx, [rsp+68h+pv]; pv
0x180015286  mov     [rsp+68h+pv], 0
0x18001528f  test    rcx, rcx
0x180015292  jz      short loc_18001529A
0x180015294  call    cs:__imp_CoTaskMemFree
0x18001529a  mov     r14, [r14]
0x18001529d  test    r14, r14
0x1800152a0  jnz     short loc_1800152C1
0x1800152a2  mov     ecx, 8007000Eh
0x1800152a7  mov     esi, ecx
0x1800152a9  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_PLATFORM@@SAEXZ; _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel(void)
0x1800152ae  cmp     al, dil
0x1800152b1  jb      loc_180015359
0x1800152b7  mov     edx, 0D2h
0x1800152bc  jmp     loc_18001523A
0x1800152c1  xor     esi, esi
0x1800152c3  mov     [r14], edi
0x1800152c6  call    cs:__imp_MFGetSystemTime
0x1800152cc  mov     [r14+8], rax
0x1800152d0  cmp     [rbx+270h], sil
0x1800152d7  jnz     short loc_18001534C
0x1800152d9  lea     eax, [rsi+3]
0x1800152dc  mov     [rbx+2C8h], dil
0x1800152e3  mov     [rbx+3F4h], eax
0x1800152e9  xorps   xmm0, xmm0
0x1800152ec  mov     [rbx+3FCh], eax
0x1800152f2  xorps   xmm1, xmm1
0x1800152f5  mov     rax, 8000000000000000h
0x1800152ff  mov     [rbx+231h], sil
0x180015306  mov     [rbx+2E0h], rax
0x18001530d  xor     dil, dil
0x180015310  mov     [rbx+3B8h], rax
0x180015317  mov     [rbx+234h], esi
0x18001531d  mov     [rbx+378h], si
0x180015324  mov     dword ptr [rbx+3F0h], 2
0x18001532e  movdqu  xmmword ptr [rbx+330h], xmm0
0x180015336  mov     [rbx+2E8h], rsi
0x18001533d  movdqu  xmmword ptr [rbx+340h], xmm1
0x180015345  mov     [rbx+2F0h], rsi
0x18001534c  mov     [rbx+2C9h], dil
0x180015353  mov     [rbx+4448h], esi
0x180015359  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_CORE_MFTS@@SAEXZ; _MFControlLevel_CTRLGUID_MF_CORE_MFTS::GetLevel(void)
0x18001535e  cmp     al, 20h ; ' '
0x180015360  jb      short loc_180015388
0x180015362  mov     rcx, cs:WPP_GLOBAL_Control
0x180015369  lea     r8, WPP_45b7a7f164d436fa30fa2a10d6f3fbff_Traceguids
0x180015370  mov     edx, 0D3h
0x180015375  mov     [rsp+68h+var_48], esi
0x180015379  mov     r9, rbx
0x18001537c  mov     rcx, [rcx+0D8h]
0x180015383  call    WPP_SF_qD
0x180015388  mov     rcx, r15; lpCriticalSection
0x18001538b  call    cs:__imp_LeaveCriticalSection
0x180015391  mov     rcx, rbp; lpCriticalSection
0x180015394  call    cs:__imp_LeaveCriticalSection
0x18001539a  mov     eax, esi
0x18001539c  add     rsp, 38h
0x1800153a0  pop     r15
0x1800153a2  pop     r14
0x1800153a4  pop     rdi
0x1800153a5  pop     rsi
0x1800153a6  pop     rbp
0x1800153a7  pop     rbx
0x1800153a8  retn
```
