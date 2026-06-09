# Streaming::Utils::GetProcessAndUserNotSystem(_FLT_CALLBACK_DATA &,appv::shared::kernel::managed_unicode_string<appv::shared::kernel::UnicodeString_allocator> &,void * &)

- ea: `0x140014c40`
- end: `0x140014d31`
- name: `?GetProcessAndUserNotSystem@Utils@Streaming@@YAJAEAU_FLT_CALLBACK_DATA@@AEAV?$managed_unicode_string@UUnicodeString_allocator@kernel@shared@appv@@@kernel@shared@appv@@AEAPEAX@Z`
- size: `241`
- prototype: `__int64 __fastcall(PFLT_CALLBACK_DATA CallbackData)`
- caller_count: `2`
- callee_count: `5`
- tags: `authz_impersonation`

## callers

- `0x14000a310`
- `0x14000da20`

## callees

- `0x140003770`
- `0x140014560`
- `0x140014640`
- `0x140014934`
- `0x140014c40`

## import_xrefs

- `ntoskrnl!RtlInitUnicodeString` at `0x140014cfd`
- `ntoskrnl!RtlInitUnicodeString` at `0x140014cfd`
- `FLTMGR!FltGetRequestorProcessIdEx` at `0x140014c80`
- `FLTMGR!FltGetRequestorProcessIdEx` at `0x140014d0c`
- `FLTMGR!FltGetRequestorProcessIdEx` at `0x140014c80`
- `FLTMGR!FltGetRequestorProcessIdEx` at `0x140014d0c`

## pseudocode

```c
__int64 __fastcall Streaming::Utils::GetProcessAndUserNotSystem(
        PFLT_CALLBACK_DATA CallbackData,
        __int64 a2,
        HANDLE *a3)
{
  struct _KTHREAD *Thread; // rcx
  int v7; // edi
  HANDLE RequestorProcessId; // rax
  const WCHAR *v10; // rdx
  unsigned int v11; // ecx
  __int16 v12; // dx
  __int16 v13; // ax
  char v14; // [rsp+40h] [rbp+8h] BYREF

  v14 = 1;
  Thread = CallbackData->Thread;
  if ( !Thread
    || (v7 = appv::shared::kernel::SidFromEThread<appv::shared::kernel::UnicodeString_allocator>(Thread, a2, &v14),
        v7 == -1073741700) )
  {
    RequestorProcessId = FltGetRequestorProcessIdEx(CallbackData);
    v7 = appv::shared::kernel::SidFromPid<appv::shared::kernel::UnicodeString_allocator>(
           RequestorProcessId,
           a2,
           (__int64)&v14);
  }
  if ( v7 == -1073741813 )
    return Streaming::Utils::GetCurrentProcessAndUserNotSystem(a2, a3);
  if ( v7 >= 0 )
  {
    if ( v14 )
    {
      appv::shared::kernel::buffer<appv::shared::kernel::UnicodeString_allocator>::resize(a2, 0);
      if ( *(_DWORD *)a2 )
      {
        v11 = *(_DWORD *)a2 >> 1;
        if ( v11 > 0xFFFF )
          v12 = -1;
        else
          v12 = *(_DWORD *)a2 >> 1;
        v13 = 0;
        if ( v11 <= 0xFFFF )
          v13 = v12;
        v10 = 0;
        if ( v13 )
          v10 = *(const WCHAR **)(a2 + 8);
      }
      else
      {
        v10 = 0;
      }
      RtlInitUnicodeString((PUNICODE_STRING)(a2 + 16), v10);
    }
    *a3 = FltGetRequestorProcessIdEx(CallbackData);
  }
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x140014c40  mov     rax, rsp
0x140014c43  mov     [rax+10h], rbx
0x140014c47  mov     [rax+18h], rbp
0x140014c4b  push    rsi
0x140014c4c  push    rdi
0x140014c4d  push    r14
0x140014c4f  sub     rsp, 20h
0x140014c53  mov     rsi, rcx
0x140014c56  mov     byte ptr [rax+8], 1
0x140014c5a  mov     rcx, [rcx+8]
0x140014c5e  xor     ebp, ebp
0x140014c60  mov     r14, r8
0x140014c63  mov     rbx, rdx
0x140014c66  test    rcx, rcx
0x140014c69  jz      short loc_140014C7D
0x140014c6b  lea     r8, [rax+8]
0x140014c6f  call    ??$SidFromEThread@UUnicodeString_allocator@kernel@shared@appv@@@kernel@shared@appv@@YAJPEAU_KTHREAD@@AEAV?$managed_unicode_string@UUnicodeString_allocator@kernel@shared@appv@@@012@PEAE@Z; appv::shared::kernel::SidFromEThread<appv::shared::kernel::UnicodeString_allocator>(_KTHREAD *,appv::shared::kernel::managed_unicode_string<appv::shared::kernel::UnicodeString_allocator> &,uchar *)
0x140014c74  mov     edi, eax
0x140014c76  cmp     eax, 0C000007Ch
0x140014c7b  jnz     short loc_140014C9E
0x140014c7d  mov     rcx, rsi; CallbackData
0x140014c80  call    cs:__imp_FltGetRequestorProcessIdEx
0x140014c87  nop     dword ptr [rax+rax+00h]
0x140014c8c  lea     r8, [rsp+38h+arg_0]
0x140014c91  mov     rdx, rbx
0x140014c94  mov     rcx, rax
0x140014c97  call    ??$SidFromPid@UUnicodeString_allocator@kernel@shared@appv@@@kernel@shared@appv@@YAJPEAXAEAV?$managed_unicode_string@UUnicodeString_allocator@kernel@shared@appv@@@012@PEAE@Z; appv::shared::kernel::SidFromPid<appv::shared::kernel::UnicodeString_allocator>(void *,appv::shared::kernel::managed_unicode_string<appv::shared::kernel::UnicodeString_allocator> &,uchar *)
0x140014c9c  mov     edi, eax
0x140014c9e  cmp     edi, 0C000000Bh
0x140014ca4  jnz     short loc_140014CB3
0x140014ca6  mov     rdx, r14
0x140014ca9  mov     rcx, rbx
0x140014cac  call    ?GetCurrentProcessAndUserNotSystem@Utils@Streaming@@YAJAEAV?$managed_unicode_string@UUnicodeString_allocator@kernel@shared@appv@@@kernel@shared@appv@@AEAPEAX@Z; Streaming::Utils::GetCurrentProcessAndUserNotSystem(appv::shared::kernel::managed_unicode_string<appv::shared::kernel::UnicodeString_allocator> &,void * &)
0x140014cb1  jmp     short loc_140014D1D
0x140014cb3  test    edi, edi
0x140014cb5  js      short loc_140014D1B
0x140014cb7  cmp     [rsp+38h+arg_0], bpl
0x140014cbc  jz      short loc_140014D09
0x140014cbe  xor     edx, edx
0x140014cc0  mov     rcx, rbx
0x140014cc3  call    ?resize@?$buffer@UUnicodeString_allocator@kernel@shared@appv@@@kernel@shared@appv@@QEAAJK@Z; appv::shared::kernel::buffer<appv::shared::kernel::UnicodeString_allocator>::resize(ulong)
0x140014cc8  mov     ecx, [rbx]
0x140014cca  test    ecx, ecx
0x140014ccc  jnz     short loc_140014CD2
0x140014cce  xor     edx, edx
0x140014cd0  jmp     short loc_140014CF9
0x140014cd2  shr     ecx, 1
0x140014cd4  mov     r8d, 0FFFFh
0x140014cda  cmp     ecx, r8d
0x140014cdd  ja      short loc_140014CE4
0x140014cdf  movzx   edx, cx
0x140014ce2  jmp     short loc_140014CE7
0x140014ce4  mov     edx, r8d
0x140014ce7  mov     eax, ebp
0x140014ce9  cmovbe  ax, dx
0x140014ced  mov     rdx, rbp
0x140014cf0  test    ax, ax
0x140014cf3  jz      short loc_140014CF9
0x140014cf5  mov     rdx, [rbx+8]; SourceString
0x140014cf9  lea     rcx, [rbx+10h]; DestinationString
0x140014cfd  call    cs:__imp_RtlInitUnicodeString
0x140014d04  nop     dword ptr [rax+rax+00h]
0x140014d09  mov     rcx, rsi; CallbackData
0x140014d0c  call    cs:__imp_FltGetRequestorProcessIdEx
0x140014d13  nop     dword ptr [rax+rax+00h]
0x140014d18  mov     [r14], rax
0x140014d1b  mov     eax, edi
0x140014d1d  mov     rbx, [rsp+38h+arg_8]
0x140014d22  mov     rbp, [rsp+38h+arg_10]
0x140014d27  add     rsp, 20h
0x140014d2b  pop     r14
0x140014d2d  pop     rdi
0x140014d2e  pop     rsi
0x140014d2f  retn
```
