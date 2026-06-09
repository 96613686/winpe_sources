# GlyphFactoryManager::SetPendingState(LockHolder const &,IGlyphFactory *)

- ea: `0x18006d3e4`
- end: `0x18006d4c1`
- name: `?SetPendingState@GlyphFactoryManager@@AEAAXAEBVLockHolder@@PEAVIGlyphFactory@@@Z`
- size: `221`
- prototype: `void __fastcall(GlyphFactoryManager *__hidden this, const struct LockHolder *, struct IGlyphFactory *)`
- caller_count: `2`
- callee_count: `3`
- tags: ``

## callers

- `0x18006cb80`
- `0x18006cee0`

## callees

- `0x18006d3e4`
- `0x1800aa650`
- `0x1800ab180`

## import_xrefs

- `api-ms-win-core-threadpool-l1-2-0!SubmitThreadpoolWork` at `0x18006d43f`
- `api-ms-win-core-threadpool-l1-2-0!SubmitThreadpoolWork` at `0x18006d43f`
- `api-ms-win-core-sysinfo-l1-1-0!GlobalMemoryStatusEx` at `0x18006d47c`
- `api-ms-win-core-sysinfo-l1-1-0!GlobalMemoryStatusEx` at `0x18006d47c`

## pseudocode

```c
void __fastcall GlyphFactoryManager::SetPendingState(
        GlyphFactoryManager *this,
        const struct LockHolder *a2,
        struct IGlyphFactory *a3)
{
  __int64 v3; // rax
  unsigned int v5; // eax
  _MEMORYSTATUSEX Buffer; // [rsp+20h] [rbp-58h] BYREF

  v3 = *((_QWORD *)this + 47);
  if ( v3 )
  {
    *((_QWORD *)a3 + 3) = v3;
    *(_QWORD *)(*((_QWORD *)this + 47) + 32LL) = a3;
  }
  else
  {
    *((_QWORD *)this + 46) = a3;
  }
  *((_QWORD *)this + 47) = a3;
  *((_DWORD *)a3 + 4) = 2;
  v5 = *((_DWORD *)this + 97);
  if ( !v5 )
  {
    memset_0(&Buffer, 0, sizeof(Buffer));
    if ( GlobalMemoryStatusEx(&Buffer) )
    {
      if ( Buffer.ullTotalPhys >> 30 )
      {
        v5 = 4;
        if ( Buffer.ullTotalPhys >> 30 < 4 )
          v5 = Buffer.ullTotalPhys >> 30;
      }
      else
      {
        v5 = 1;
      }
      *((_DWORD *)this + 97) = v5;
    }
    else
    {
      *((_DWORD *)this + 97) = 1;
      v5 = 1;
    }
  }
  if ( *((_DWORD *)this + 96) < v5 )
  {
    SubmitThreadpoolWork(*((PTP_WORK *)this + 41));
    ++*((_DWORD *)this + 96);
  }
}

```

## disassembly

```asm
0x18006d3e4  push    rbx
0x18006d3e6  sub     rsp, 70h
0x18006d3ea  mov     rax, cs:__security_cookie
0x18006d3f1  xor     rax, rsp
0x18006d3f4  mov     [rsp+78h+var_18], rax
0x18006d3f9  mov     rax, [rcx+178h]
0x18006d400  mov     rbx, rcx
0x18006d403  test    rax, rax
0x18006d406  jz      short loc_18006D45E
0x18006d408  mov     [r8+18h], rax
0x18006d40c  mov     rax, [rcx+178h]
0x18006d413  mov     [rax+20h], r8
0x18006d417  mov     [rcx+178h], r8
0x18006d41e  mov     dword ptr [r8+10h], 2
0x18006d426  mov     eax, [rcx+184h]
0x18006d42c  test    eax, eax
0x18006d42e  jz      short loc_18006D467
0x18006d430  cmp     [rbx+180h], eax
0x18006d436  jnb     short loc_18006D44B
0x18006d438  mov     rcx, [rbx+148h]; pwk
0x18006d43f  call    cs:__imp_SubmitThreadpoolWork
0x18006d445  inc     dword ptr [rbx+180h]
0x18006d44b  mov     rcx, [rsp+78h+var_18]
0x18006d450  xor     rcx, rsp; StackCookie
0x18006d453  call    __security_check_cookie
0x18006d458  add     rsp, 70h
0x18006d45c  pop     rbx
0x18006d45d  retn
0x18006d45e  mov     [rcx+170h], r8
0x18006d465  jmp     short loc_18006D417
0x18006d467  xor     edx, edx; Val
0x18006d469  lea     rcx, [rsp+78h+Buffer]; void *
0x18006d46e  lea     r8d, [rdx+40h]; Size
0x18006d472  call    memset_0
0x18006d477  lea     rcx, [rsp+78h+Buffer]; lpBuffer
0x18006d47c  call    cs:__imp_GlobalMemoryStatusEx
0x18006d482  test    eax, eax
0x18006d484  jnz     short loc_18006D497
0x18006d486  mov     dword ptr [rbx+184h], 1
0x18006d490  mov     eax, 1
0x18006d495  jmp     short loc_18006D430
0x18006d497  mov     rcx, [rsp+78h+Buffer.ullTotalPhys]
0x18006d49c  shr     rcx, 1Eh
0x18006d4a0  test    rcx, rcx
0x18006d4a3  jnz     short loc_18006D4AA
0x18006d4a5  lea     eax, [rcx+1]
0x18006d4a8  jmp     short loc_18006D4B6
0x18006d4aa  mov     eax, 4
0x18006d4af  cmp     rcx, rax
0x18006d4b2  jnb     short loc_18006D4B6
0x18006d4b4  mov     eax, ecx
0x18006d4b6  mov     [rbx+184h], eax
0x18006d4bc  jmp     loc_18006D430
```
