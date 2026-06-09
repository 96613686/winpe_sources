# Windows::ApplicationModel::Resources::Core::CResourceCandidate::GetValueAsStream(Windows::Storage::Streams::IRandomAccessStream * *)

- ea: `0x180058670`
- end: `0x1800588ab`
- name: `?GetValueAsStream@CResourceCandidate@Core@Resources@ApplicationModel@Windows@@EEAAJPEAPEAUIRandomAccessStream@Streams@Storage@5@@Z`
- size: `571`
- prototype: `__int64 __fastcall(Windows::ApplicationModel::Resources::Core::CResourceCandidate *__hidden this, struct Windows::Storage::Streams::IRandomAccessStream **)`
- caller_count: `0`
- callee_count: `11`
- tags: `broker_com_uri`

## callees

- `0x18000892c`
- `0x18002c8d0`
- `0x180039ec8`
- `0x180039ef0`
- `0x18003a694`
- `0x18003ac44`
- `0x18003ae3c`
- `0x18003bccc`
- `0x180058670`
- `0x1800588b4`
- `0x1800c5010`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180058821`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180058891`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180058821`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180058891`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180058830`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800588a0`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180058830`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800588a0`
- `api-ms-win-shcore-stream-winrt-l1-1-0!CreateRandomAccessStreamOnFile` at `0x18005880f`
- `api-ms-win-shcore-stream-winrt-l1-1-0!CreateRandomAccessStreamOnFile` at `0x18005880f`
- `api-ms-win-shcore-stream-winrt-l1-1-0!CreateRandomAccessStreamOverStream` at `0x18005879a`
- `api-ms-win-shcore-stream-winrt-l1-1-0!CreateRandomAccessStreamOverStream` at `0x18005879a`
- `SHCORE!__imp_SHCreateMemoryStreamOnSharedBuffer` at `0x18005877a`
- `SHCORE!__imp_SHCreateMemoryStreamOnSharedBuffer` at `0x18005877a`

## string_xrefs

- `0x180058840`: `onecoreuap\base\mrt\runtime\com\winrt\core\winrtresourcecandidate.cpp`
- `0x180058866`: `onecoreuap\base\mrt\runtime\com\winrt\core\winrtresourcecandidate.cpp`
- `0x1800c37f5`: `onecoreuap\base\mrt\runtime\com\winrt\core\winrtresourcecandidate.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall Windows::ApplicationModel::Resources::Core::CResourceCandidate::GetValueAsStream(
        Microsoft::Resources::Runtime::CResolvedInstanceInternal **this,
        struct Windows::Storage::Streams::IRandomAccessStream **a2)
{
  int ResourceValueType; // ebx
  unsigned int v5; // ecx
  int ValueData; // eax
  int RandomAccessStreamOverStream; // eax
  __int64 v9; // rcx
  HANDLE ProcessHeap; // rax
  __int64 v11; // rdx
  __int64 v12; // rdx
  HANDLE v13; // rax
  __int64 v14; // [rsp+20h] [rbp-10h] BYREF
  LPVOID v15; // [rsp+28h] [rbp-8h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+58h] [rbp+28h]
  bool v17; // [rsp+60h] [rbp+30h] BYREF
  unsigned int v18; // [rsp+68h] [rbp+38h] BYREF
  LPVOID lpMem; // [rsp+70h] [rbp+40h] BYREF
  __int64 v20; // [rsp+78h] [rbp+48h] BYREF

  *a2 = 0;
  v18 = 0;
  ResourceValueType = Microsoft::Resources::Runtime::CResolvedInstanceInternal::GetResourceValueType(
                        this[10],
                        (enum Microsoft::Resources::MrmEnvironment::ResourceValueType *)&v18);
  if ( ResourceValueType < 0 )
  {
    v11 = 403;
LABEL_23:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v11,
      (unsigned int)"onecoreuap\\base\\mrt\\runtime\\com\\winrt\\core\\winrtresourcecandidate.cpp",
      (const char *)(unsigned int)ResourceValueType,
      v14);
    return (unsigned int)ResourceValueType;
  }
  if ( (unsigned __int8)Microsoft::Resources::MrmEnvironment::IsPathResourceValueType(v18) )
  {
    lpMem = 0;
    v17 = 0;
    ResourceValueType = Microsoft::Resources::Runtime::CResolvedInstanceInternal::GetValueStringByType(
                          (__int64)this[10],
                          v5,
                          (const unsigned __int16 **)&lpMem,
                          &v17);
    if ( ResourceValueType >= 0 )
    {
      ResourceValueType = CreateRandomAccessStreamOnFile(lpMem, 0, &GUID_905a0fe1_bc53_11df_8c49_001e4fc686da, a2);
      if ( v17 )
      {
        ProcessHeap = GetProcessHeap();
        HeapFree(ProcessHeap, 0, lpMem);
      }
      return (unsigned int)ResourceValueType;
    }
    v11 = 408;
    goto LABEL_23;
  }
  if ( v5 != 2 )
    return 2147957517LL;
  v15 = 0;
  LODWORD(lpMem) = 0;
  v17 = 0;
  v14 = 0;
  ValueData = Microsoft::Resources::Runtime::CResolvedInstanceInternal::GetValueData(
                this[10],
                (const void **)&v15,
                (unsigned int *)&lpMem,
                &v17);
  ResourceValueType = ValueData;
  if ( ValueData < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x1A9,
      (unsigned int)"onecoreuap\\base\\mrt\\runtime\\com\\winrt\\core\\winrtresourcecandidate.cpp",
      (const char *)(unsigned int)ValueData,
      v14);
LABEL_29:
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IIterator<Windows::ApplicationModel::Resources::Core::ResourceQualifier *>>::InternalRelease(&v14);
    return (unsigned int)ResourceValueType;
  }
  v20 = 0;
  Microsoft::WRL::ComPtr<StreamBufferHelper>::InternalRelease(&v20);
  ResourceValueType = Microsoft::WRL::Details::MakeAndInitialize<StreamBufferHelper,StreamBufferHelper,void const * &,unsigned int,bool &>(
                        &v20,
                        &v15,
                        &lpMem,
                        &v17);
  if ( ResourceValueType < 0 )
  {
    if ( v17 )
    {
      v13 = GetProcessHeap();
      HeapFree(v13, 0, v15);
    }
    if ( v20 )
    {
      v20 = 0;
      Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,Windows::Storage::Streams::IBufferByteAccess,Microsoft::WRL::FtmBase>::Release();
    }
    return (unsigned int)ResourceValueType;
  }
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IIterator<Windows::ApplicationModel::Resources::Core::ResourceQualifier *>>::InternalRelease(&v14);
  RandomAccessStreamOverStream = SHCreateMemoryStreamOnSharedBuffer(v20, *(unsigned int *)(v20 + 56), &v14);
  ResourceValueType = RandomAccessStreamOverStream;
  if ( RandomAccessStreamOverStream < 0 )
  {
    v12 = 431;
LABEL_28:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v12,
      (unsigned int)"onecoreuap\\base\\mrt\\runtime\\com\\winrt\\core\\winrtresourcecandidate.cpp",
      (const char *)(unsigned int)RandomAccessStreamOverStream,
      v14);
    Microsoft::WRL::ComPtr<StreamBufferHelper>::InternalRelease(&v20);
    goto LABEL_29;
  }
  RandomAccessStreamOverStream = CreateRandomAccessStreamOverStream(
                                   v14,
                                   0,
                                   &GUID_905a0fe1_bc53_11df_8c49_001e4fc686da,
                                   a2);
  ResourceValueType = RandomAccessStreamOverStream;
  if ( RandomAccessStreamOverStream < 0 )
  {
    v12 = 443;
    goto LABEL_28;
  }
  if ( v20 )
  {
    v20 = 0;
    Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,Windows::Storage::Streams::IBufferByteAccess,Microsoft::WRL::FtmBase>::Release();
  }
  v9 = v14;
  if ( v14 )
  {
    v14 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v9 + 16LL))(v9);
  }
  return 0;
}

```

## disassembly

```asm
0x180058670  push    rbp
0x180058672  push    rbx
0x180058673  push    rsi
0x180058674  push    rdi
0x180058675  push    r14
0x180058677  mov     rbp, rsp
0x18005867a  sub     rsp, 30h
0x18005867e  mov     rsi, rdx
0x180058681  mov     rdi, rcx
0x180058684  xor     r14d, r14d
0x180058687  mov     [rdx], r14
0x18005868a  mov     [rbp+arg_8], r14d
0x18005868e  lea     rdx, [rbp+arg_8]; enum Microsoft::Resources::MrmEnvironment::ResourceValueType *
0x180058692  mov     rcx, [rcx+50h]; this
0x180058696  call    ?GetResourceValueType@CResolvedInstanceInternal@Runtime@Resources@Microsoft@@QEBAJPEAW4ResourceValueType@MrmEnvironment@34@@Z; Microsoft::Resources::Runtime::CResolvedInstanceInternal::GetResourceValueType(Microsoft::Resources::MrmEnvironment::ResourceValueType *)
0x18005869b  mov     ebx, eax
0x18005869d  test    eax, eax
0x18005869f  js      loc_18005883B
0x1800586a5  mov     ecx, [rbp+arg_8]
0x1800586a8  call    ?IsPathResourceValueType@MrmEnvironment@Resources@Microsoft@@SA_NW4ResourceValueType@123@@Z; Microsoft::Resources::MrmEnvironment::IsPathResourceValueType(Microsoft::Resources::MrmEnvironment::ResourceValueType)
0x1800586ad  test    al, al
0x1800586af  jnz     loc_1800587DE
0x1800586b5  cmp     ecx, 2
0x1800586b8  jnz     loc_18005875F
0x1800586be  mov     [rbp+var_8], r14
0x1800586c2  mov     dword ptr [rbp+lpMem], r14d
0x1800586c6  mov     [rbp+arg_0], r14b
0x1800586ca  mov     [rbp+var_10], r14
0x1800586ce  lea     r9, [rbp+arg_0]; bool *
0x1800586d2  lea     r8, [rbp+lpMem]; unsigned int *
0x1800586d6  lea     rdx, [rbp+var_8]; void **
0x1800586da  mov     rcx, [rdi+50h]; this
0x1800586de  call    ?GetValueData@CResolvedInstanceInternal@Runtime@Resources@Microsoft@@QEBAJPEAPEBXPEAIPEA_N@Z; Microsoft::Resources::Runtime::CResolvedInstanceInternal::GetValueData(void const * *,uint *,bool *)
0x1800586e3  mov     ebx, eax
0x1800586e5  test    eax, eax
0x1800586e7  js      loc_18005885F
0x1800586ed  mov     [rbp+arg_18], r14
0x1800586f1  mov     eax, dword ptr [rbp+lpMem]
0x1800586f4  mov     dword ptr [rbp+lpMem], eax
0x1800586f7  lea     rcx, [rbp+arg_18]
0x1800586fb  call    ?InternalRelease@?$ComPtr@VStreamBufferHelper@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<StreamBufferHelper>::InternalRelease(void)
0x180058700  lea     r9, [rbp+arg_0]
0x180058704  lea     r8, [rbp+lpMem]
0x180058708  lea     rdx, [rbp+var_8]
0x18005870c  lea     rcx, [rbp+arg_18]
0x180058710  call    ??$MakeAndInitialize@VStreamBufferHelper@@V1@AEAPEBXIAEA_N@Details@WRL@Microsoft@@YAJPEAPEAVStreamBufferHelper@@AEAPEBX$$QEAIAEA_N@Z; Microsoft::WRL::Details::MakeAndInitialize<StreamBufferHelper,StreamBufferHelper,void const * &,uint,bool &>(StreamBufferHelper * *,void const * &,uint &&,bool &)
0x180058715  mov     ebx, eax
0x180058717  test    eax, eax
0x180058719  jns     short loc_180058766
0x18005871b  cmp     [rbp+arg_0], r14b
0x18005871f  jnz     loc_180058891
0x180058725  mov     rcx, [rbp+arg_18]
0x180058729  test    rcx, rcx
0x18005872c  jz      short loc_180058738
0x18005872e  mov     [rbp+arg_18], r14
0x180058732  call    ?Release@?$RuntimeClassImpl@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00$0A@$0A@UIBufferByteAccess@Streams@Storage@Windows@@VFtmBase@23@@Details@WRL@Microsoft@@UEAAKXZ; Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,Windows::Storage::Streams::IBufferByteAccess,Microsoft::WRL::FtmBase>::Release(void)
0x180058737  nop
0x180058738  mov     rcx, [rbp+var_10]
0x18005873c  test    rcx, rcx
0x18005873f  jz      short loc_180058752
0x180058741  mov     [rbp+var_10], r14
0x180058745  mov     rax, [rcx]
0x180058748  mov     rax, [rax+10h]
0x18005874c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180058751  nop
0x180058752  mov     eax, ebx
0x180058754  add     rsp, 30h
0x180058758  pop     r14
0x18005875a  pop     rdi
0x18005875b  pop     rsi
0x18005875c  pop     rbx
0x18005875d  pop     rbp
0x18005875e  retn
0x18005875f  mov     eax, 80073B0Dh
0x180058764  jmp     short loc_180058754
0x180058766  lea     rcx, [rbp+var_10]
0x18005876a  call    ?InternalRelease@?$ComPtr@U?$IIterator@PEAVResourceQualifier@Core@Resources@ApplicationModel@Windows@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IIterator<Windows::ApplicationModel::Resources::Core::ResourceQualifier *>>::InternalRelease(void)
0x18005876f  mov     rcx, [rbp+arg_18]
0x180058773  lea     r8, [rbp+var_10]
0x180058777  mov     edx, [rcx+38h]
0x18005877a  call    cs:__imp_SHCreateMemoryStreamOnSharedBuffer
0x180058780  mov     ebx, eax
0x180058782  test    eax, eax
0x180058784  js      loc_18005887D
0x18005878a  mov     r9, rsi
0x18005878d  lea     r8, _GUID_905a0fe1_bc53_11df_8c49_001e4fc686da
0x180058794  xor     edx, edx
0x180058796  mov     rcx, [rbp+var_10]
0x18005879a  call    cs:__imp_CreateRandomAccessStreamOverStream
0x1800587a0  mov     ebx, eax
0x1800587a2  test    eax, eax
0x1800587a4  js      loc_180058887
0x1800587aa  mov     rcx, [rbp+arg_18]
0x1800587ae  test    rcx, rcx
0x1800587b1  jz      short loc_1800587BD
0x1800587b3  mov     [rbp+arg_18], r14
0x1800587b7  call    ?Release@?$RuntimeClassImpl@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00$0A@$0A@UIBufferByteAccess@Streams@Storage@Windows@@VFtmBase@23@@Details@WRL@Microsoft@@UEAAKXZ; Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,Windows::Storage::Streams::IBufferByteAccess,Microsoft::WRL::FtmBase>::Release(void)
0x1800587bc  nop
0x1800587bd  mov     rcx, [rbp+var_10]
0x1800587c1  test    rcx, rcx
0x1800587c4  jz      short loc_1800587D7
0x1800587c6  mov     [rbp+var_10], r14
0x1800587ca  mov     rax, [rcx]
0x1800587cd  mov     rax, [rax+10h]
0x1800587d1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800587d6  nop
0x1800587d7  xor     eax, eax
0x1800587d9  jmp     loc_180058754
0x1800587de  mov     [rbp+lpMem], r14
0x1800587e2  mov     [rbp+arg_0], r14b
0x1800587e6  lea     r9, [rbp+arg_0]
0x1800587ea  lea     r8, [rbp+lpMem]
0x1800587ee  mov     edx, ecx
0x1800587f0  mov     rcx, [rdi+50h]
0x1800587f4  call    ?GetValueStringByType@CResolvedInstanceInternal@Runtime@Resources@Microsoft@@QEBAJW4ResourceValueType@MrmEnvironment@34@PEAPEBGPEA_N@Z; Microsoft::Resources::Runtime::CResolvedInstanceInternal::GetValueStringByType(Microsoft::Resources::MrmEnvironment::ResourceValueType,ushort const * *,bool *)
0x1800587f9  mov     ebx, eax
0x1800587fb  test    eax, eax
0x1800587fd  js      short loc_180058858
0x1800587ff  mov     r9, rsi
0x180058802  lea     r8, _GUID_905a0fe1_bc53_11df_8c49_001e4fc686da
0x180058809  xor     edx, edx
0x18005880b  mov     rcx, [rbp+lpMem]
0x18005880f  call    cs:__imp_CreateRandomAccessStreamOnFile
0x180058815  mov     ebx, eax
0x180058817  cmp     [rbp+arg_0], r14b
0x18005881b  jz      loc_180058752
0x180058821  call    cs:__imp_GetProcessHeap
0x180058827  mov     r8, [rbp+lpMem]; lpMem
0x18005882b  xor     edx, edx; dwFlags
0x18005882d  mov     rcx, rax; hHeap
0x180058830  call    cs:__imp_HeapFree
0x180058836  jmp     loc_180058752
0x18005883b  mov     edx, 193h; void *
0x180058840  lea     r8, aOnecoreuapBase_20; "onecoreuap\\base\\mrt\\runtime\\com\\wi"...
0x180058847  mov     r9d, ebx; char *
0x18005884a  mov     rcx, [rbp+28h]; this
0x18005884e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180058853  jmp     loc_180058752
0x180058858  mov     edx, 198h
0x18005885d  jmp     short loc_180058840
0x18005885f  mov     rcx, [rbp+28h]; this
0x180058863  mov     r9d, eax; char *
0x180058866  lea     r8, aOnecoreuapBase_20; "onecoreuap\\base\\mrt\\runtime\\com\\wi"...
0x18005886d  mov     edx, 1A9h; void *
0x180058872  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180058877  nop
0x180058878  jmp     loc_1800C380E
0x18005887d  mov     edx, 1AFh; void *
0x180058882  jmp     loc_1800C37F2
0x180058887  mov     edx, 1BBh
0x18005888c  jmp     loc_1800C37F2
0x180058891  call    cs:__imp_GetProcessHeap
0x180058897  mov     r8, [rbp+var_8]; lpMem
0x18005889b  xor     edx, edx; dwFlags
0x18005889d  mov     rcx, rax; hHeap
0x1800588a0  call    cs:__imp_HeapFree
0x1800588a6  jmp     loc_180058725
0x1800c37f2  mov     r9d, eax; char *
0x1800c37f5  lea     r8, aOnecoreuapBase_20; "onecoreuap\\base\\mrt\\runtime\\com\\wi"...
0x1800c37fc  mov     rcx, [rbp+28h]; this
0x1800c3800  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800c3805  lea     rcx, [rbp+arg_18]
0x1800c3809  call    ?InternalRelease@?$ComPtr@VStreamBufferHelper@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<StreamBufferHelper>::InternalRelease(void)
0x1800c380e  lea     rcx, [rbp+var_10]
0x1800c3812  call    ?InternalRelease@?$ComPtr@U?$IIterator@PEAVResourceQualifier@Core@Resources@ApplicationModel@Windows@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IIterator<Windows::ApplicationModel::Resources::Core::ResourceQualifier *>>::InternalRelease(void)
0x1800c3817  nop
0x1800c3818  jmp     loc_180058752
```
