# CIVIAudioCodec::~CIVIAudioCodec(void)

- ea: `0x180018e90`
- end: `0x180018fe8`
- name: `??1CIVIAudioCodec@@UEAA@XZ`
- size: `344`
- prototype: `void __fastcall(CIVIAudioCodec *__hidden this)`
- caller_count: `3`
- callee_count: `5`
- tags: `file_ops, service_task, broker_com_uri`

## callers

- `0x18000aa40`
- `0x180018ff0`
- `0x180088850`

## callees

- `0x180001b80`
- `0x18000afe0`
- `0x180018e90`
- `0x180019030`
- `0x180033bf0`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__aligned_free` at `0x180018ef5`
- `api-ms-win-crt-private-l1-1-0!_o__aligned_free` at `0x180018ef5`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180018f8f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180018fbe`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180018f8f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180018fbe`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180018f51`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180018f51`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180018f61`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180018f74`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180018f61`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180018f74`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180018f2d`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180018f2d`
- `api-ms-win-eventing-provider-l1-1-0!EventUnregister` at `0x180018f41`
- `api-ms-win-eventing-provider-l1-1-0!EventUnregister` at `0x180018f41`

## pseudocode

```c
void __fastcall CIVIAudioCodec::~CIVIAudioCodec(CIVIAudioCodec *this, unsigned int a2)
{
  Mpegtoraw *v3; // rcx
  void *v4; // rcx
  unsigned int v5; // edx
  CSpeakerFill *v6; // rcx

  *(_QWORD *)this = &CIVIAudioCodec::`vftable';
  v3 = (Mpegtoraw *)*((_QWORD *)this + 780);
  if ( v3 )
    Mpegtoraw::`scalar deleting destructor'(v3, a2);
  *((_QWORD *)this + 780) = 0;
  v4 = (void *)*((_QWORD *)this + 795);
  if ( v4 )
    operator delete(v4);
  *((_QWORD *)this + 795) = 0;
  if ( *((_QWORD *)this + 801) )
    AACAudioDecoderClose((void **)this + 801);
  _aligned_free(*((void **)this + 794));
  *((_QWORD *)this + 794) = 0;
  v6 = (CSpeakerFill *)*((_QWORD *)this + 1892);
  if ( v6 )
  {
    CSpeakerFill::`scalar deleting destructor'(v6, v5);
    *((_QWORD *)this + 1892) = 0;
  }
  if ( this != (CIVIAudioCodec *)-24LL )
  {
    EnterCriticalSection((LPCRITICAL_SECTION)this + 1);
    if ( !*((_DWORD *)this + 6) )
      EventUnregister(*((_QWORD *)this + 4));
    LeaveCriticalSection((LPCRITICAL_SECTION)this + 1);
    DeleteCriticalSection((LPCRITICAL_SECTION)this + 1);
  }
  DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 304));
  if ( *((_DWORD *)this + 70) )
  {
    CoTaskMemFree(*((LPVOID *)this + 36));
    *((_DWORD *)this + 70) = 0;
    *((_QWORD *)this + 36) = 0;
  }
  *((_QWORD *)this + 34) = 0;
  if ( *((_DWORD *)this + 48) )
  {
    CoTaskMemFree(*((LPVOID *)this + 25));
    *((_DWORD *)this + 48) = 0;
    *((_QWORD *)this + 25) = 0;
  }
  *((_QWORD *)this + 23) = 0;
}

```

## disassembly

```asm
0x180018e90  push    rbx
0x180018e92  push    rbp
0x180018e93  push    rsi
0x180018e94  push    rdi
0x180018e95  sub     rsp, 28h
0x180018e99  mov     rbx, rcx
0x180018e9c  lea     rax, ??_7CIVIAudioCodec@@6B@; const CIVIAudioCodec::`vftable'
0x180018ea3  mov     [rcx], rax
0x180018ea6  mov     rcx, [rcx+1860h]; this
0x180018ead  test    rcx, rcx
0x180018eb0  jz      short loc_180018EB7
0x180018eb2  call    ??_GMpegtoraw@@QEAAPEAXI@Z; Mpegtoraw::`scalar deleting destructor'(uint)
0x180018eb7  xor     ebp, ebp
0x180018eb9  mov     [rbx+1860h], rbp
0x180018ec0  mov     rcx, [rbx+18D8h]; Block
0x180018ec7  test    rcx, rcx
0x180018eca  jz      short loc_180018ED6
0x180018ecc  mov     edx, 28h ; '('
0x180018ed1  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180018ed6  mov     [rbx+18D8h], rbp
0x180018edd  lea     rcx, [rbx+1908h]
0x180018ee4  cmp     [rcx], rbp
0x180018ee7  jz      short loc_180018EEE
0x180018ee9  call    AACAudioDecoderClose
0x180018eee  mov     rcx, [rbx+18D0h]; Block
0x180018ef5  call    cs:__imp__aligned_free
0x180018efc  nop     dword ptr [rax+rax+00h]
0x180018f01  mov     [rbx+18D0h], rbp
0x180018f08  mov     rcx, [rbx+3B20h]; this
0x180018f0f  test    rcx, rcx
0x180018f12  jz      short loc_180018F20
0x180018f14  call    ??_GCSpeakerFill@@QEAAPEAXI@Z; CSpeakerFill::`scalar deleting destructor'(uint)
0x180018f19  mov     [rbx+3B20h], rbp
0x180018f20  lea     rdi, [rbx+18h]
0x180018f24  test    rdi, rdi
0x180018f27  jz      short loc_180018F6D
0x180018f29  lea     rcx, [rdi+10h]; lpCriticalSection
0x180018f2d  call    cs:__imp_EnterCriticalSection
0x180018f34  nop     dword ptr [rax+rax+00h]
0x180018f39  cmp     [rdi], ebp
0x180018f3b  jnz     short loc_180018F4D
0x180018f3d  mov     rcx, [rdi+8]; RegHandle
0x180018f41  call    cs:__imp_EventUnregister
0x180018f48  nop     dword ptr [rax+rax+00h]
0x180018f4d  lea     rcx, [rdi+10h]; lpCriticalSection
0x180018f51  call    cs:__imp_LeaveCriticalSection
0x180018f58  nop     dword ptr [rax+rax+00h]
0x180018f5d  lea     rcx, [rdi+10h]; lpCriticalSection
0x180018f61  call    cs:__imp_DeleteCriticalSection
0x180018f68  nop     dword ptr [rax+rax+00h]
0x180018f6d  lea     rcx, [rbx+130h]; lpCriticalSection
0x180018f74  call    cs:__imp_DeleteCriticalSection
0x180018f7b  nop     dword ptr [rax+rax+00h]
0x180018f80  cmp     [rbx+118h], ebp
0x180018f86  jz      short loc_180018FA8
0x180018f88  mov     rcx, [rbx+120h]; pv
0x180018f8f  call    cs:__imp_CoTaskMemFree
0x180018f96  nop     dword ptr [rax+rax+00h]
0x180018f9b  mov     [rbx+118h], ebp
0x180018fa1  mov     [rbx+120h], rbp
0x180018fa8  mov     [rbx+110h], rbp
0x180018faf  cmp     [rbx+0C0h], ebp
0x180018fb5  jz      short loc_180018FD7
0x180018fb7  mov     rcx, [rbx+0C8h]; pv
0x180018fbe  call    cs:__imp_CoTaskMemFree
0x180018fc5  nop     dword ptr [rax+rax+00h]
0x180018fca  mov     [rbx+0C0h], ebp
0x180018fd0  mov     [rbx+0C8h], rbp
0x180018fd7  mov     [rbx+0B8h], rbp
0x180018fde  add     rsp, 28h
0x180018fe2  pop     rdi
0x180018fe3  pop     rsi
0x180018fe4  pop     rbp
0x180018fe5  pop     rbx
0x180018fe6  retn
```
