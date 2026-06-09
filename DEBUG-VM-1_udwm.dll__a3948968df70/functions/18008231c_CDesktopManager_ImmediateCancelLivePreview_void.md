# CDesktopManager::ImmediateCancelLivePreview(void)

- ea: `0x18008231c`
- end: `0x1800823eb`
- name: `?ImmediateCancelLivePreview@CDesktopManager@@QEAAJXZ`
- size: `207`
- prototype: `__int64 __fastcall(CDesktopManager *__hidden this)`
- caller_count: `2`
- callee_count: `4`
- tags: ``

## callers

- `0x18002d650`
- `0x18007d570`

## callees

- `0x18001f43c`
- `0x18008231c`
- `0x1800827d0`
- `0x180083f40`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18008239d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18008239d`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18008237c`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18008237c`
- `USER32!PostThreadMessageW` at `0x180082393`
- `USER32!PostThreadMessageW` at `0x180082393`

## pseudocode

```c
__int64 __fastcall CDesktopManager::ImmediateCancelLivePreview(CDesktopManager *this)
{
  _QWORD *v2; // rax
  void *v3; // rdi
  signed int v4; // ebx
  signed int LastError; // eax
  unsigned int v7; // [rsp+20h] [rbp-18h]

  v2 = DefaultHeap::Alloc(0x20u);
  v3 = v2;
  if ( v2 )
  {
    *v2 = 0;
    v2[1] = 0;
    *((_DWORD *)v2 + 4) = 1;
    v2[3] = 1;
    SetLastError(0);
    if ( PostThreadMessageW(*((_DWORD *)this + 282), 0x405u, (WPARAM)v3, 0) )
    {
      v4 = 0;
      v3 = 0;
      goto LABEL_11;
    }
    LastError = GetLastError();
    v4 = LastError;
    if ( LastError > 0 )
      v4 = (unsigned __int16)LastError | 0x80070000;
    v7 = 2735;
    if ( v4 >= 0 )
      v4 = -2003304445;
  }
  else
  {
    v4 = -2147024882;
    v7 = 2721;
  }
  MilInstrumentationCheckHR_MaybeFailFast(0x14u, 0, 0, v4, v7, 0);
LABEL_11:
  DefaultHeap::Free(v3);
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x18008231c  mov     [rsp+arg_0], rbx
0x180082321  push    rdi
0x180082322  sub     rsp, 30h
0x180082326  mov     rbx, rcx
0x180082329  mov     ecx, 20h ; ' '; unsigned __int64
0x18008232e  call    ?Alloc@DefaultHeap@@SAPEAX_K@Z; DefaultHeap::Alloc(unsigned __int64)
0x180082333  mov     rdi, rax
0x180082336  test    rax, rax
0x180082339  jnz     short loc_18008235F
0x18008233b  mov     [rsp+38h+var_10], rax; void *
0x180082340  mov     ebx, 8007000Eh
0x180082345  mov     [rsp+38h+var_18], 0AA1h; unsigned int
0x18008234d  xor     edx, edx; int *
0x18008234f  mov     r9d, ebx; int
0x180082352  xor     r8d, r8d; unsigned int
0x180082355  lea     ecx, [rdx+14h]; unsigned int
0x180082358  call    ?MilInstrumentationCheckHR_MaybeFailFast@@YAXKQEBJIJIPEAX@Z; MilInstrumentationCheckHR_MaybeFailFast(ulong,long const * const,uint,long,uint,void *)
0x18008235d  jmp     short loc_1800823D6
0x18008235f  mov     qword ptr [rax], 0
0x180082366  xor     ecx, ecx; dwErrCode
0x180082368  mov     qword ptr [rax+8], 0
0x180082370  mov     eax, 1
0x180082375  mov     [rdi+10h], eax
0x180082378  mov     [rdi+18h], rax
0x18008237c  call    cs:__imp_SetLastError
0x180082382  mov     ecx, [rbx+468h]; idThread
0x180082388  xor     r9d, r9d; lParam
0x18008238b  mov     r8, rdi; wParam
0x18008238e  mov     edx, 405h; Msg
0x180082393  call    cs:__imp_PostThreadMessageW
0x180082399  test    eax, eax
0x18008239b  jnz     short loc_1800823D2
0x18008239d  call    cs:__imp_GetLastError
0x1800823a3  mov     ebx, eax
0x1800823a5  test    eax, eax
0x1800823a7  jle     short loc_1800823B2
0x1800823a9  movzx   ebx, ax
0x1800823ac  or      ebx, 80070000h
0x1800823b2  test    ebx, ebx
0x1800823b4  mov     [rsp+38h+var_10], 0
0x1800823bd  mov     eax, 88980003h
0x1800823c2  mov     [rsp+38h+var_18], 0AAFh
0x1800823ca  cmovns  ebx, eax
0x1800823cd  jmp     loc_18008234D
0x1800823d2  xor     ebx, ebx
0x1800823d4  xor     edi, edi
0x1800823d6  mov     rcx, rdi; lpMem
0x1800823d9  call    ?Free@DefaultHeap@@SAXPEAX@Z; DefaultHeap::Free(void *)
0x1800823de  mov     eax, ebx
0x1800823e0  mov     rbx, [rsp+38h+arg_0]
0x1800823e5  add     rsp, 30h
0x1800823e9  pop     rdi
0x1800823ea  retn
```
