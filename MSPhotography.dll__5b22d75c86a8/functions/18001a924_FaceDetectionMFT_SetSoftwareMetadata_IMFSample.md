# FaceDetectionMFT::SetSoftwareMetadata(IMFSample *)

- ea: `0x18001a924`
- end: `0x18001aacd`
- name: `?SetSoftwareMetadata@FaceDetectionMFT@@AEAAJPEAUIMFSample@@@Z`
- size: `425`
- prototype: `__int64 __fastcall(FaceDetectionMFT *__hidden this, struct IMFSample *)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180016af0`

## callees

- `0x180005660`
- `0x18000b490`
- `0x18000c0f8`
- `0x18001a924`
- `0x180142010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001a948`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001a948`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001aab7`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001aab7`
- `MFPlat!MFCreateAttributes` at `0x18001a9b8`
- `MFPlat!MFCreateAttributes` at `0x18001a9b8`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall FaceDetectionMFT::SetSoftwareMetadata(FaceDetectionMFT *this, struct IMFSample *a2)
{
  HRESULT v4; // ebx
  struct _RTL_CRITICAL_SECTION *v5; // rsi
  HRESULT (__stdcall *GetUnknown)(IMFSample *, const GUID *const, const IID *const, LPVOID *); // rbx
  __int64 v7; // rdx
  IMFAttributes *ppMFAttributes; // [rsp+50h] [rbp+8h] BYREF
  char *v10; // [rsp+60h] [rbp+18h]

  v4 = 0;
  v5 = (struct _RTL_CRITICAL_SECTION *)((char *)this + 464);
  v10 = (char *)this + 464;
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 464));
  ppMFAttributes = 0;
  if ( !*((_QWORD *)this + 122) || !*((_QWORD *)this + 123) )
    goto LABEL_17;
  GetUnknown = a2->lpVtbl->GetUnknown;
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&ppMFAttributes);
  if ( ((int (__fastcall *)(struct IMFSample *, const GUID *, GUID *, IMFAttributes **))GetUnknown)(
         a2,
         &MFSampleExtension_CaptureMetadata,
         &GUID_2cd2d921_c447_44a7_a13c_4adabfc247e3,
         &ppMFAttributes) >= 0 )
    goto LABEL_10;
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&ppMFAttributes);
  v4 = MFCreateAttributes(&ppMFAttributes, 1u);
  if ( v4 < 0 )
  {
    if ( _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
    {
      v7 = 97;
LABEL_16:
      WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), v7, &WPP_45b7a7f164d436fa30fa2a10d6f3fbff_Traceguids, this, v4);
      goto LABEL_17;
    }
    goto LABEL_17;
  }
  v4 = ((__int64 (__fastcall *)(struct IMFSample *, const GUID *, IMFAttributes *))a2->lpVtbl->SetUnknown)(
         a2,
         &MFSampleExtension_CaptureMetadata,
         ppMFAttributes);
  if ( v4 >= 0 )
  {
LABEL_10:
    v4 = ((__int64 (__fastcall *)(IMFAttributes *, const GUID *, _QWORD, _QWORD))ppMFAttributes->lpVtbl->SetBlob)(
           ppMFAttributes,
           &MF_CAPTURE_METADATA_FACEROIS,
           *((_QWORD *)this + 122),
           **((unsigned int **)this + 122));
    if ( v4 >= 0 )
    {
      v4 = ((__int64 (__fastcall *)(IMFAttributes *, const GUID *, _QWORD, __int64))ppMFAttributes->lpVtbl->SetBlob)(
             ppMFAttributes,
             &MF_CAPTURE_METADATA_FACEROITIMESTAMPS,
             *((_QWORD *)this + 123),
             24);
      if ( v4 < 0 && _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
      {
        v7 = 100;
        goto LABEL_16;
      }
    }
    else if ( _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
    {
      v7 = 99;
      goto LABEL_16;
    }
    goto LABEL_17;
  }
  if ( _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
  {
    v7 = 98;
    goto LABEL_16;
  }
LABEL_17:
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&ppMFAttributes);
  LeaveCriticalSection(v5);
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x18001a924  mov     [rsp+arg_8], rbx
0x18001a929  push    rsi
0x18001a92a  push    rdi
0x18001a92b  push    r14
0x18001a92d  sub     rsp, 30h
0x18001a931  mov     r14, rdx
0x18001a934  mov     rdi, rcx
0x18001a937  xor     ebx, ebx
0x18001a939  lea     rsi, [rcx+1D0h]
0x18001a940  mov     [rsp+48h+arg_10], rsi
0x18001a945  mov     rcx, rsi; lpCriticalSection
0x18001a948  call    cs:__imp_EnterCriticalSection
0x18001a94e  nop
0x18001a94f  mov     [rsp+48h+ppMFAttributes], rbx
0x18001a954  cmp     [rdi+3D0h], rbx
0x18001a95b  jz      loc_18001AAA9
0x18001a961  cmp     [rdi+3D8h], rbx
0x18001a968  jz      loc_18001AAA9
0x18001a96e  mov     rax, [r14]
0x18001a971  mov     rbx, [rax+88h]
0x18001a978  lea     rcx, [rsp+48h+ppMFAttributes]
0x18001a97d  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18001a982  lea     r9, [rsp+48h+ppMFAttributes]
0x18001a987  lea     r8, _GUID_2cd2d921_c447_44a7_a13c_4adabfc247e3
0x18001a98e  lea     rdx, MFSampleExtension_CaptureMetadata
0x18001a995  mov     rcx, r14
0x18001a998  mov     rax, rbx
0x18001a99b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001a9a0  test    eax, eax
0x18001a9a2  jns     short loc_18001AA13
0x18001a9a4  lea     rcx, [rsp+48h+ppMFAttributes]
0x18001a9a9  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18001a9ae  mov     edx, 1; cInitialSize
0x18001a9b3  lea     rcx, [rsp+48h+ppMFAttributes]; ppMFAttributes
0x18001a9b8  call    cs:__imp_MFCreateAttributes
0x18001a9be  mov     ebx, eax
0x18001a9c0  test    eax, eax
0x18001a9c2  jns     short loc_18001A9DB
0x18001a9c4  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_PLATFORM@@SAEXZ; _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel(void)
0x18001a9c9  cmp     al, 1
0x18001a9cb  jb      loc_18001AAA9
0x18001a9d1  mov     edx, 61h ; 'a'
0x18001a9d6  jmp     loc_18001AA8A
0x18001a9db  mov     rax, [r14]
0x18001a9de  mov     r8, [rsp+48h+ppMFAttributes]
0x18001a9e3  lea     rdx, MFSampleExtension_CaptureMetadata
0x18001a9ea  mov     rcx, r14
0x18001a9ed  mov     rax, [rax+0D8h]
0x18001a9f4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001a9f9  mov     ebx, eax
0x18001a9fb  test    eax, eax
0x18001a9fd  jns     short loc_18001AA13
0x18001a9ff  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_PLATFORM@@SAEXZ; _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel(void)
0x18001aa04  cmp     al, 1
0x18001aa06  jb      loc_18001AAA9
0x18001aa0c  mov     edx, 62h ; 'b'
0x18001aa11  jmp     short loc_18001AA8A
0x18001aa13  mov     r8, [rdi+3D0h]
0x18001aa1a  mov     rcx, [rsp+48h+ppMFAttributes]
0x18001aa1f  mov     rax, [rcx]
0x18001aa22  mov     r9d, [r8]
0x18001aa25  lea     rdx, MF_CAPTURE_METADATA_FACEROIS
0x18001aa2c  mov     rax, [rax+0D0h]
0x18001aa33  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001aa38  mov     ebx, eax
0x18001aa3a  test    eax, eax
0x18001aa3c  jns     short loc_18001AA4E
0x18001aa3e  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_PLATFORM@@SAEXZ; _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel(void)
0x18001aa43  cmp     al, 1
0x18001aa45  jb      short loc_18001AAA9
0x18001aa47  mov     edx, 63h ; 'c'
0x18001aa4c  jmp     short loc_18001AA8A
0x18001aa4e  mov     rcx, [rsp+48h+ppMFAttributes]
0x18001aa53  mov     rax, [rcx]
0x18001aa56  mov     r9d, 18h
0x18001aa5c  mov     r8, [rdi+3D8h]
0x18001aa63  lea     rdx, MF_CAPTURE_METADATA_FACEROITIMESTAMPS
0x18001aa6a  mov     rax, [rax+0D0h]
0x18001aa71  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001aa76  mov     ebx, eax
0x18001aa78  test    eax, eax
0x18001aa7a  jns     short loc_18001AAA9
0x18001aa7c  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_PLATFORM@@SAEXZ; _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel(void)
0x18001aa81  cmp     al, 1
0x18001aa83  jb      short loc_18001AAA9
0x18001aa85  mov     edx, 64h ; 'd'
0x18001aa8a  mov     rcx, cs:WPP_GLOBAL_Control
0x18001aa91  mov     [rsp+48h+var_28], ebx
0x18001aa95  mov     r9, rdi
0x18001aa98  lea     r8, WPP_45b7a7f164d436fa30fa2a10d6f3fbff_Traceguids
0x18001aa9f  mov     rcx, [rcx+10h]
0x18001aaa3  call    WPP_SF_qD
0x18001aaa8  nop
0x18001aaa9  lea     rcx, [rsp+48h+ppMFAttributes]
0x18001aaae  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18001aab3  nop
0x18001aab4  mov     rcx, rsi; lpCriticalSection
0x18001aab7  call    cs:__imp_LeaveCriticalSection
0x18001aabd  mov     eax, ebx
0x18001aabf  mov     rbx, [rsp+48h+arg_8]
0x18001aac4  add     rsp, 30h
0x18001aac8  pop     r14
0x18001aaca  pop     rdi
0x18001aacb  pop     rsi
0x18001aacc  retn
```
