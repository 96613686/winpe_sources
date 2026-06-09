# UpdateReserveManager::ModifyUpdateScratchReserveSize(IUpdateReserveManagerCBS::UpdateSizeType,unsigned __int64)

- ea: `0x18001a968`
- end: `0x18001ac0c`
- name: `?ModifyUpdateScratchReserveSize@UpdateReserveManager@@AEAAJW4UpdateSizeType@IUpdateReserveManagerCBS@@_K@Z`
- size: `676`
- prototype: `__int64 __fastcall(HANDLE *, int, unsigned __int64)`
- caller_count: `2`
- callee_count: `8`
- tags: `file_ops, loader_planting, installer_update`

## callers

- `0x18001d140`
- `0x180020e00`

## callees

- `0x180003870`
- `0x180003c84`
- `0x1800044e0`
- `0x18000fafc`
- `0x180015ad0`
- `0x18001a968`
- `0x1800248e0`
- `0x180033010`

## import_xrefs

- `ntdll!NtFsControlFile` at `0x18001aaa8`
- `ntdll!NtFsControlFile` at `0x18001aaa8`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x18001aac2`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x18001aac2`

## string_xrefs

- `0x18001aad7`: `onecore\base\servicing\updatereservemanager\lib\updatereservemanager.cpp`
- `0x18001ab20`: `onecore\base\servicing\updatereservemanager\lib\updatereservemanager.cpp`
- `0x18001ab79`: `onecore\base\servicing\updatereservemanager\lib\updatereservemanager.cpp`
- `0x18001aba0`: `onecore\base\servicing\updatereservemanager\lib\updatereservemanager.cpp`
- `0x18001aae2`: `UpdateReserveManager::ModifyUpdateScratchReserveSize`
- `0x18001ab2b`: `UpdateReserveManager::ModifyUpdateScratchReserveSize`
- `0x18001ab84`: `UpdateReserveManager::ModifyUpdateScratchReserveSize`
- `0x18001abab`: `UpdateReserveManager::ModifyUpdateScratchReserveSize`
- `0x18001abbe`: `::ULongLongAdd(UpdateScratchSize, SizeInBytes, &NewUpdateScratchSize)`
- `0x18001ab97`: `::ULongLongToLongLong(NewUpdateScratchSize, &SignedUpdateScratchReserveSize)`

## pseudocode

```c
__int64 __fastcall UpdateReserveManager::ModifyUpdateScratchReserveSize(HANDLE *a1, int a2, unsigned __int64 a3)
{
  __int64 result; // rax
  unsigned int i; // esi
  unsigned __int64 v8; // rbx
  _DWORD *InputBuffer; // rdi
  int v10; // ecx
  unsigned int v11; // ebx
  const char *v12; // rax
  const char *v13; // [rsp+58h] [rbp-29h] BYREF
  const char *v14; // [rsp+60h] [rbp-21h]
  __int64 v15; // [rsp+68h] [rbp-19h]
  const char *v16; // [rsp+70h] [rbp-11h]
  _DWORD *v17; // [rsp+78h] [rbp-9h]
  __int64 v18; // [rsp+80h] [rbp-1h]
  __int128 v19; // [rsp+88h] [rbp+7h] BYREF
  __int64 v20; // [rsp+98h] [rbp+17h]
  struct _IO_STATUS_BLOCK IoStatusBlock; // [rsp+A0h] [rbp+1Fh] BYREF

  v18 = -2;
  result = UpdateReserveManager::EnsureNotInSafeMode((UpdateReserveManager *)a1);
  if ( (int)result >= 0 )
  {
    for ( i = 0; ; ++i )
    {
      v19 = 0;
      v20 = 0;
      result = (*((__int64 (__fastcall **)(HANDLE *, _QWORD, __int64, __int128 *))*a1 + 4))(a1, 0, 6, &v19);
      if ( (int)result < 0 )
        return result;
      if ( a2 )
      {
        if ( a2 != 1 )
        {
          v13 = "onecore\\base\\servicing\\updatereservemanager\\lib\\updatereservemanager.cpp";
          v14 = "UpdateReserveManager::ModifyUpdateScratchReserveSize";
          v15 = 3873;
          v16 = "((HRESULT)0x8000FFFFL)";
          RtlReportErrorOrigination(&v13, &GUID_e323b7c4_7a1a_4e06_bf6d_56ccd7377627, 2147549183LL);
          return 2147549183LL;
        }
        v8 = (v19 - a3) & -(__int64)(a3 < (unsigned __int64)v19);
      }
      else
      {
        v8 = v19 + a3;
        if ( (unsigned __int64)v19 + a3 < (unsigned __int64)v19 )
        {
          v13 = "onecore\\base\\servicing\\updatereservemanager\\lib\\updatereservemanager.cpp";
          v14 = "UpdateReserveManager::ModifyUpdateScratchReserveSize";
          v15 = 3857;
          v12 = "::ULongLongAdd(UpdateScratchSize, SizeInBytes, &NewUpdateScratchSize)";
          goto LABEL_17;
        }
      }
      if ( v8 > 0x7FFFFFFFFFFFFFFFLL )
      {
        v13 = "onecore\\base\\servicing\\updatereservemanager\\lib\\updatereservemanager.cpp";
        v14 = "UpdateReserveManager::ModifyUpdateScratchReserveSize";
        v15 = 3877;
        v12 = "::ULongLongToLongLong(NewUpdateScratchSize, &SignedUpdateScratchReserveSize)";
LABEL_17:
        v16 = v12;
        RtlReportErrorOrigination(&v13, &GUID_e323b7c4_7a1a_4e06_bf6d_56ccd7377627, 2147942934LL);
        return 2147942934LL;
      }
      InputBuffer = operator new[](0x20u);
      v17 = InputBuffer;
      *InputBuffer = 1;
      InputBuffer[1] = 1;
      InputBuffer[2] = 16;
      InputBuffer[3] = 1;
      InputBuffer[4] = 3;
      InputBuffer[5] = 1;
      *((_QWORD *)InputBuffer + 3) = v8;
      IoStatusBlock = 0;
      v10 = NtFsControlFile(a1[16], 0, 0, 0, &IoStatusBlock, 0x90410u, InputBuffer, 0x20u, 0, 0);
      if ( v10 >= 0 )
      {
        operator delete(InputBuffer);
        return 0;
      }
      if ( i >= 2 )
      {
        v13 = "onecore\\base\\servicing\\updatereservemanager\\lib\\updatereservemanager.cpp";
        v14 = "UpdateReserveManager::ModifyUpdateScratchReserveSize";
        v15 = 3920;
        v16 = 0;
        v11 = ConvertNtStatusToHResult(v10);
        RtlReportErrorOrigination(&v13, &GUID_e323b7c4_7a1a_4e06_bf6d_56ccd7377627, v11);
        operator delete(InputBuffer);
        return v11;
      }
      Sleep(0x3E8u);
      operator delete(InputBuffer);
    }
  }
  return result;
}

```

## disassembly

```asm
0x18001a968  mov     rax, rsp
0x18001a96b  push    rbp
0x18001a96c  push    rdi
0x18001a96d  push    r12
0x18001a96f  push    r14
0x18001a971  push    r15
0x18001a973  lea     rbp, [rax-5Fh]
0x18001a977  sub     rsp, 0B0h
0x18001a97e  mov     [rbp+57h+var_58], 0FFFFFFFFFFFFFFFEh
0x18001a986  mov     [rax+10h], rbx
0x18001a98a  mov     [rax+18h], rsi
0x18001a98e  mov     rax, cs:__security_cookie
0x18001a995  xor     rax, rsp
0x18001a998  mov     [rbp+57h+var_28], rax
0x18001a99c  mov     r14, r8
0x18001a99f  mov     r12d, edx
0x18001a9a2  mov     r15, rcx
0x18001a9a5  call    ?EnsureNotInSafeMode@UpdateReserveManager@@AEAAJXZ; UpdateReserveManager::EnsureNotInSafeMode(void)
0x18001a9aa  test    eax, eax
0x18001a9ac  js      loc_18001ABE4
0x18001a9b2  xor     esi, esi
0x18001a9b4  xorps   xmm0, xmm0
0x18001a9b7  xor     eax, eax
0x18001a9b9  movups  [rbp+57h+var_50], xmm0
0x18001a9bd  mov     [rbp+57h+var_40], rax
0x18001a9c1  mov     rax, [r15]
0x18001a9c4  lea     r9, [rbp+57h+var_50]
0x18001a9c8  xor     edx, edx
0x18001a9ca  lea     r8d, [rdx+6]
0x18001a9ce  mov     rcx, r15
0x18001a9d1  mov     rax, [rax+20h]
0x18001a9d5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001a9da  test    eax, eax
0x18001a9dc  js      loc_18001ABE4
0x18001a9e2  mov     rcx, qword ptr [rbp+57h+var_50]
0x18001a9e6  mov     eax, r12d
0x18001a9e9  test    r12d, r12d
0x18001a9ec  jz      short loc_18001AA08
0x18001a9ee  cmp     eax, 1
0x18001a9f1  jnz     loc_18001AAD7
0x18001a9f7  mov     rax, rcx
0x18001a9fa  sub     rax, r14
0x18001a9fd  cmp     r14, rcx
0x18001aa00  sbb     rbx, rbx
0x18001aa03  and     rbx, rax
0x18001aa06  jmp     short loc_18001AA15
0x18001aa08  lea     rbx, [rcx+r14]
0x18001aa0c  cmp     rbx, rcx
0x18001aa0f  jb      loc_18001ABA0
0x18001aa15  mov     rax, 7FFFFFFFFFFFFFFFh
0x18001aa1f  cmp     rbx, rax
0x18001aa22  ja      loc_18001AB79
0x18001aa28  mov     [rbp+57h+var_60], 0
0x18001aa30  mov     ecx, 20h ; ' '; unsigned __int64
0x18001aa35  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x18001aa3a  mov     rdi, rax
0x18001aa3d  mov     [rbp+57h+var_60], rax
0x18001aa41  mov     eax, 1
0x18001aa46  mov     [rdi], eax
0x18001aa48  mov     [rdi+4], eax
0x18001aa4b  mov     dword ptr [rdi+8], 10h
0x18001aa52  mov     [rdi+0Ch], eax
0x18001aa55  mov     dword ptr [rdi+10h], 3
0x18001aa5c  mov     [rdi+14h], eax
0x18001aa5f  mov     [rdi+18h], rbx
0x18001aa63  xorps   xmm0, xmm0
0x18001aa66  movups  xmmword ptr [rbp+57h+var_38], xmm0
0x18001aa6a  mov     [rsp+0D0h+OutputBufferLength], 0; OutputBufferLength
0x18001aa72  mov     [rsp+0D0h+OutputBuffer], 0; OutputBuffer
0x18001aa7b  mov     [rsp+0D0h+InputBufferLength], 20h ; ' '; InputBufferLength
0x18001aa83  mov     [rsp+0D0h+InputBuffer], rdi; InputBuffer
0x18001aa88  mov     [rsp+0D0h+FsControlCode], 90410h; FsControlCode
0x18001aa90  lea     rax, [rbp+57h+var_38]
0x18001aa94  mov     [rsp+0D0h+IoStatusBlock], rax; IoStatusBlock
0x18001aa99  xor     r9d, r9d; ApcContext
0x18001aa9c  xor     r8d, r8d; ApcRoutine
0x18001aa9f  xor     edx, edx; Event
0x18001aaa1  mov     rcx, [r15+80h]; FileHandle
0x18001aaa8  call    cs:__imp_NtFsControlFile
0x18001aaae  mov     ecx, eax; Status
0x18001aab0  test    eax, eax
0x18001aab2  jns     loc_18001AB6D
0x18001aab8  cmp     esi, 2
0x18001aabb  jnb     short loc_18001AB20
0x18001aabd  mov     ecx, 3E8h; dwMilliseconds
0x18001aac2  call    cs:__imp_Sleep
0x18001aac8  inc     esi
0x18001aaca  mov     rcx, rdi; void *
0x18001aacd  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18001aad2  jmp     loc_18001A9B4
0x18001aad7  lea     rax, aOnecoreBaseSer_1; "onecore\\base\\servicing\\updatereserve"...
0x18001aade  mov     [rbp+57h+var_80], rax
0x18001aae2  lea     rax, aUpdatereservem_50; "UpdateReserveManager::ModifyUpdateScrat"...
0x18001aae9  mov     [rbp+57h+var_78], rax
0x18001aaed  mov     [rbp+57h+var_70], 0F21h
0x18001aaf5  lea     rax, aHresult0x8000f; "((HRESULT)0x8000FFFFL)"
0x18001aafc  mov     [rbp+57h+var_68], rax
0x18001ab00  mov     r8d, 8000FFFFh
0x18001ab06  lea     rdx, _GUID_e323b7c4_7a1a_4e06_bf6d_56ccd7377627
0x18001ab0d  lea     rcx, [rbp+57h+var_80]
0x18001ab11  call    RtlReportErrorOrigination
0x18001ab16  mov     eax, 8000FFFFh
0x18001ab1b  jmp     loc_18001ABE4
0x18001ab20  lea     rax, aOnecoreBaseSer_1; "onecore\\base\\servicing\\updatereserve"...
0x18001ab27  mov     [rbp+57h+var_80], rax
0x18001ab2b  lea     rax, aUpdatereservem_50; "UpdateReserveManager::ModifyUpdateScrat"...
0x18001ab32  mov     [rbp+57h+var_78], rax
0x18001ab36  mov     [rbp+57h+var_70], 0F50h
0x18001ab3e  mov     [rbp+57h+var_68], 0
0x18001ab46  call    ConvertNtStatusToHResult
0x18001ab4b  mov     ebx, eax
0x18001ab4d  mov     r8d, eax
0x18001ab50  lea     rdx, _GUID_e323b7c4_7a1a_4e06_bf6d_56ccd7377627
0x18001ab57  lea     rcx, [rbp+57h+var_80]
0x18001ab5b  call    RtlReportErrorOrigination
0x18001ab60  nop
0x18001ab61  mov     rcx, rdi; void *
0x18001ab64  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18001ab69  mov     eax, ebx
0x18001ab6b  jmp     short loc_18001ABE4
0x18001ab6d  mov     rcx, rdi; void *
0x18001ab70  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18001ab75  xor     eax, eax
0x18001ab77  jmp     short loc_18001ABE4
0x18001ab79  lea     rax, aOnecoreBaseSer_1; "onecore\\base\\servicing\\updatereserve"...
0x18001ab80  mov     [rbp+57h+var_80], rax
0x18001ab84  lea     rax, aUpdatereservem_50; "UpdateReserveManager::ModifyUpdateScrat"...
0x18001ab8b  mov     [rbp+57h+var_78], rax
0x18001ab8f  mov     [rbp+57h+var_70], 0F25h
0x18001ab97  lea     rax, aUlonglongtolon_0; "::ULongLongToLongLong(NewUpdateScratchS"...
0x18001ab9e  jmp     short loc_18001ABC5
0x18001aba0  lea     rax, aOnecoreBaseSer_1; "onecore\\base\\servicing\\updatereserve"...
0x18001aba7  mov     [rbp+57h+var_80], rax
0x18001abab  lea     rax, aUpdatereservem_50; "UpdateReserveManager::ModifyUpdateScrat"...
0x18001abb2  mov     [rbp+57h+var_78], rax
0x18001abb6  mov     [rbp+57h+var_70], 0F11h
0x18001abbe  lea     rax, aUlonglongaddUp; "::ULongLongAdd(UpdateScratchSize, SizeI"...
0x18001abc5  mov     [rbp+57h+var_68], rax
0x18001abc9  mov     r8d, 80070216h
0x18001abcf  lea     rdx, _GUID_e323b7c4_7a1a_4e06_bf6d_56ccd7377627
0x18001abd6  lea     rcx, [rbp+57h+var_80]
0x18001abda  call    RtlReportErrorOrigination
0x18001abdf  mov     eax, 80070216h
0x18001abe4  mov     rcx, [rbp+57h+var_28]
0x18001abe8  xor     rcx, rsp; StackCookie
0x18001abeb  call    __security_check_cookie
0x18001abf0  lea     r11, [rsp+0D0h+var_20]
0x18001abf8  mov     rbx, [r11+38h]
0x18001abfc  mov     rsi, [r11+40h]
0x18001ac00  mov     rsp, r11
0x18001ac03  pop     r15
0x18001ac05  pop     r14
0x18001ac07  pop     r12
0x18001ac09  pop     rdi
0x18001ac0a  pop     rbp
0x18001ac0b  retn
```
