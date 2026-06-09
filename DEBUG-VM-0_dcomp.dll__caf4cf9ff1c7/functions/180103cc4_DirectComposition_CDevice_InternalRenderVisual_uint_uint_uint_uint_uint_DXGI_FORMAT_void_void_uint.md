# DirectComposition::CDevice::InternalRenderVisual(uint,uint,uint,uint,uint,DXGI_FORMAT,void * *,void * *,uint *)

- ea: `0x180103cc4`
- end: `0x180103ea3`
- name: `?InternalRenderVisual@CDevice@DirectComposition@@QEAAJIIIIIW4DXGI_FORMAT@@PEAPEAX1PEAI@Z`
- size: `479`
- prototype: `__int64 __usercall@<rax>(DirectComposition::CDevice *__hidden this@<rcx>, unsigned int@<edx>, unsigned int@<r8d>, unsigned int@<r9d>, unsigned int, unsigned int, DXGI_FORMAT, void **, void **, unsigned int *)`
- caller_count: `2`
- callee_count: `7`
- tags: `file_ops, installer_update, broker_com_uri`

## callers

- `0x1801049c0`
- `0x1801278a0`

## callees

- `0x18001bf30`
- `0x18001d1a0`
- `0x1800827d0`
- `0x1800902b8`
- `0x180103988`
- `0x180103cc4`
- `0x180182010`

## import_xrefs

- `win32u!NtVisualCaptureBits` at `0x180103e26`
- `win32u!NtVisualCaptureBits` at `0x180103e26`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180103d23`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180103d23`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180103d31`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180103dc4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180103d31`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180103dc4`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180103e41`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180103e5a`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180103e41`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180103e5a`
- `api-ms-win-core-memory-l1-1-0!CreateFileMappingW` at `0x180103dae`
- `api-ms-win-core-memory-l1-1-0!CreateFileMappingW` at `0x180103dae`

## pseudocode

```c
__int64 __fastcall DirectComposition::CDevice::InternalRenderVisual(
        DirectComposition::CDevice *this,
        unsigned int a2,
        unsigned int a3,
        unsigned int a4,
        unsigned int a5,
        unsigned int a6,
        DXGI_FORMAT a7,
        void **a8,
        void **a9,
        unsigned int *a10)
{
  HANDLE FileMappingW; // rsi
  unsigned int v13; // r14d
  __int64 v14; // rbp
  HANDLE EventW; // rdi
  signed int LastError; // eax
  signed int v17; // ebx
  DXGI_FORMAT v18; // r15d
  unsigned __int64 dwMaximumSizeLow; // rcx
  signed int v20; // eax
  unsigned int v21; // eax
  int v22; // eax
  char *v24; // [rsp+50h] [rbp-48h] BYREF
  unsigned int v25; // [rsp+A0h] [rbp+8h] BYREF
  unsigned int v26; // [rsp+A8h] [rbp+10h]
  unsigned int v27; // [rsp+B0h] [rbp+18h]

  v27 = a3;
  v26 = a2;
  FileMappingW = 0;
  v25 = 0;
  v24 = (char *)this + 104;
  DirectComposition::CDeviceLock::Enter((DirectComposition::CDevice *)((char *)this + 104));
  v13 = a5;
  if ( !a5 || (v14 = a6) == 0 )
  {
    v17 = -2147024809;
    goto LABEL_20;
  }
  EventW = CreateEventW(0, 0, 0, 0);
  if ( EventW )
    goto LABEL_7;
  LastError = GetLastError();
  v17 = LastError;
  if ( LastError > 0 )
    v17 = (unsigned __int16)LastError | 0x80070000;
  if ( v17 >= 0 )
  {
LABEL_7:
    v18 = a7;
    v17 = HrCalcDWordAlignedScanlineStride(v13, a7, &v25);
    if ( v17 >= 0 )
    {
      dwMaximumSizeLow = v14 * v25;
      if ( dwMaximumSizeLow > 0xFFFFFFFF )
      {
        *a10 = -1;
        v17 = -2147024362;
      }
      else
      {
        *a10 = dwMaximumSizeLow;
        FileMappingW = CreateFileMappingW((HANDLE)0xFFFFFFFFFFFFFFFFLL, 0, 0x8000004u, 0, dwMaximumSizeLow, 0);
        if ( (((unsigned __int64)FileMappingW + 1) & 0xFFFFFFFFFFFFFFFEuLL) != 0 )
          goto LABEL_24;
        v20 = GetLastError();
        v17 = v20;
        if ( v20 > 0 )
          v17 = (unsigned __int16)v20 | 0x80070000;
        if ( v17 >= 0 )
        {
LABEL_24:
          DirectComposition::CDevice::FlushKernelCommands(this, 0);
          v21 = (*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)this + 21) + 8LL))(*((_QWORD *)this + 21));
          v22 = NtVisualCaptureBits(v21, v26, v27, a4, v13, v14, v18, EventW, FileMappingW);
          v17 = DirectComposition::CDevice::HRESULTFromNTSTATUS(v22);
          if ( v17 >= 0 )
            goto LABEL_21;
        }
        if ( FileMappingW )
        {
          CloseHandle(FileMappingW);
          FileMappingW = 0;
        }
      }
    }
    if ( EventW )
    {
      CloseHandle(EventW);
LABEL_20:
      EventW = 0;
    }
  }
LABEL_21:
  *a8 = FileMappingW;
  *a9 = EventW;
  CGuard<DirectComposition::CDeviceLock>::~CGuard<DirectComposition::CDeviceLock>(&v24);
  return (unsigned int)v17;
}

```

## disassembly

```asm
0x180103cc4  mov     rax, rsp
0x180103cc7  mov     [rax+20h], rbx
0x180103ccb  mov     [rax+18h], r8d
0x180103ccf  mov     [rax+10h], edx
0x180103cd2  push    rbp
0x180103cd3  push    rsi
0x180103cd4  push    rdi
0x180103cd5  push    r12
0x180103cd7  push    r13
0x180103cd9  push    r14
0x180103cdb  push    r15
0x180103cdd  sub     rsp, 60h
0x180103ce1  mov     r13, rcx
0x180103ce4  xor     esi, esi
0x180103ce6  add     rcx, 68h ; 'h'; this
0x180103cea  mov     [rax+8], esi
0x180103ced  mov     [rax-48h], rcx
0x180103cf1  mov     r12d, r9d
0x180103cf4  call    ?Enter@CDeviceLock@DirectComposition@@QEAAXXZ; DirectComposition::CDeviceLock::Enter(void)
0x180103cf9  mov     r14d, [rsp+98h+arg_20]
0x180103d01  test    r14d, r14d
0x180103d04  jz      loc_180103E62
0x180103d0a  mov     ebp, [rsp+98h+arg_28]
0x180103d11  test    ebp, ebp
0x180103d13  jz      loc_180103E62
0x180103d19  xor     r9d, r9d; lpName
0x180103d1c  xor     r8d, r8d; bInitialState
0x180103d1f  xor     edx, edx; bManualReset
0x180103d21  xor     ecx, ecx; lpEventAttributes
0x180103d23  call    cs:__imp_CreateEventW
0x180103d29  mov     rdi, rax
0x180103d2c  test    rax, rax
0x180103d2f  jnz     short loc_180103D4E
0x180103d31  call    cs:__imp_GetLastError
0x180103d37  mov     ebx, eax
0x180103d39  test    eax, eax
0x180103d3b  jle     short loc_180103D46
0x180103d3d  movzx   ebx, ax
0x180103d40  or      ebx, 80070000h
0x180103d46  test    ebx, ebx
0x180103d48  js      loc_180103E69
0x180103d4e  mov     r15d, [rsp+98h+arg_30]
0x180103d56  lea     r8, [rsp+98h+arg_0]; unsigned int *
0x180103d5e  mov     edx, r15d; enum DXGI_FORMAT
0x180103d61  mov     ecx, r14d; unsigned int
0x180103d64  call    ?HrCalcDWordAlignedScanlineStride@@YAJIW4DXGI_FORMAT@@PEAI@Z; HrCalcDWordAlignedScanlineStride(uint,DXGI_FORMAT,uint *)
0x180103d69  mov     ebx, eax
0x180103d6b  test    eax, eax
0x180103d6d  js      loc_180103E52
0x180103d73  mov     ecx, [rsp+98h+arg_0]
0x180103d7a  mov     edx, 0FFFFFFFFh
0x180103d7f  mov     rax, [rsp+98h+arg_48]
0x180103d87  imul    rcx, rbp
0x180103d8b  cmp     rcx, rdx
0x180103d8e  ja      loc_180103E4B
0x180103d94  mov     [rax], ecx
0x180103d96  xor     r9d, r9d; dwMaximumSizeHigh
0x180103d99  mov     [rsp+98h+lpName], rsi; lpName
0x180103d9e  xor     edx, edx; lpFileMappingAttributes
0x180103da0  mov     [rsp+98h+dwMaximumSizeLow], ecx; dwMaximumSizeLow
0x180103da4  mov     r8d, 8000004h; flProtect
0x180103daa  or      rcx, 0FFFFFFFFFFFFFFFFh; hFile
0x180103dae  call    cs:__imp_CreateFileMappingW
0x180103db4  mov     rsi, rax
0x180103db7  lea     rcx, [rax+1]
0x180103dbb  test    rcx, 0FFFFFFFFFFFFFFFEh
0x180103dc2  jnz     short loc_180103DDD
0x180103dc4  call    cs:__imp_GetLastError
0x180103dca  mov     ebx, eax
0x180103dcc  test    eax, eax
0x180103dce  jle     short loc_180103DD9
0x180103dd0  movzx   ebx, ax
0x180103dd3  or      ebx, 80070000h
0x180103dd9  test    ebx, ebx
0x180103ddb  js      short loc_180103E39
0x180103ddd  xor     edx, edx; bool
0x180103ddf  mov     rcx, r13; this
0x180103de2  call    ?FlushKernelCommands@CDevice@DirectComposition@@AEAAX_N@Z; DirectComposition::CDevice::FlushKernelCommands(bool)
0x180103de7  mov     rcx, [r13+0A8h]
0x180103dee  mov     rax, [rcx]
0x180103df1  mov     rax, [rax+8]
0x180103df5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180103dfa  mov     r8d, [rsp+98h+arg_10]
0x180103e02  mov     ecx, eax
0x180103e04  mov     edx, [rsp+98h+arg_8]
0x180103e0b  mov     r9d, r12d
0x180103e0e  mov     [rsp+98h+var_58], rsi
0x180103e13  mov     [rsp+98h+var_60], rdi
0x180103e18  mov     [rsp+98h+var_68], r15d
0x180103e1d  mov     dword ptr [rsp+98h+lpName], ebp
0x180103e21  mov     [rsp+98h+dwMaximumSizeLow], r14d
0x180103e26  call    cs:__imp_NtVisualCaptureBits
0x180103e2c  mov     ecx, eax; int
0x180103e2e  call    ?HRESULTFromNTSTATUS@CDevice@DirectComposition@@SAJJ@Z; DirectComposition::CDevice::HRESULTFromNTSTATUS(long)
0x180103e33  mov     ebx, eax
0x180103e35  test    eax, eax
0x180103e37  jns     short loc_180103E69
0x180103e39  test    rsi, rsi
0x180103e3c  jz      short loc_180103E52
0x180103e3e  mov     rcx, rsi; hObject
0x180103e41  call    cs:__imp_CloseHandle
0x180103e47  xor     esi, esi
0x180103e49  jmp     short loc_180103E52
0x180103e4b  mov     [rax], edx
0x180103e4d  mov     ebx, 80070216h
0x180103e52  test    rdi, rdi
0x180103e55  jz      short loc_180103E69
0x180103e57  mov     rcx, rdi; hObject
0x180103e5a  call    cs:__imp_CloseHandle
0x180103e60  jmp     short loc_180103E67
0x180103e62  mov     ebx, 80070057h
0x180103e67  xor     edi, edi
0x180103e69  mov     rax, [rsp+98h+arg_38]
0x180103e71  lea     rcx, [rsp+98h+var_48]
0x180103e76  mov     [rax], rsi
0x180103e79  mov     rax, [rsp+98h+arg_40]
0x180103e81  mov     [rax], rdi
0x180103e84  call    ??1?$CGuard@VCDeviceLock@DirectComposition@@@@QEAA@XZ; CGuard<DirectComposition::CDeviceLock>::~CGuard<DirectComposition::CDeviceLock>(void)
0x180103e89  mov     eax, ebx
0x180103e8b  mov     rbx, [rsp+98h+arg_18]
0x180103e93  add     rsp, 60h
0x180103e97  pop     r15
0x180103e99  pop     r14
0x180103e9b  pop     r13
0x180103e9d  pop     r12
0x180103e9f  pop     rdi
0x180103ea0  pop     rsi
0x180103ea1  pop     rbp
0x180103ea2  retn
```
