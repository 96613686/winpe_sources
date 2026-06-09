# GlyphFactoryManager::OnIdleTimeout(void)

- ea: `0x18006cd08`
- end: `0x18006ce3e`
- name: `?OnIdleTimeout@GlyphFactoryManager@@AEAAXXZ`
- size: `310`
- prototype: `void __fastcall(GlyphFactoryManager *__hidden this)`
- caller_count: `1`
- callee_count: `3`
- tags: `file_ops`

## callers

- `0x18006c970`

## callees

- `0x18006cd08`
- `0x18006d368`
- `0x1800e6010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18006cdf9`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18006cdf9`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18006cd29`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18006cd29`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18006cdf0`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18006cdf0`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x18006cd2f`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x18006cd2f`

## pseudocode

```c
void __fastcall GlyphFactoryManager::OnIdleTimeout(GlyphFactoryManager *this)
{
  __int64 v2; // rdi
  struct _RTL_CRITICAL_SECTION *v3; // rbx
  DWORD TickCount; // ebp
  struct IGlyphFactory **v5; // r14
  struct IGlyphFactory *v6; // r10
  __int64 v7; // r10
  __int64 v8; // r11
  __int64 *i; // rcx
  __int64 v10; // rax
  DWORD v11; // eax
  __int64 v12; // rbx
  struct _FILETIME pftDueTime; // [rsp+40h] [rbp+8h] BYREF

  v2 = 0;
  v3 = (struct _RTL_CRITICAL_SECTION *)((char *)this + 256);
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 256));
  TickCount = GetTickCount();
  v5 = (struct IGlyphFactory **)((char *)this + 336);
  v6 = (struct IGlyphFactory *)*((_QWORD *)this + 42);
  if ( v6 )
  {
    while ( TickCount - *((_DWORD *)v6 + 12) >= 0x7D0 )
    {
      GlyphFactoryManager::LinkedList::Unlink((GlyphFactoryManager *)((char *)this + 336), v6);
      for ( i = (__int64 *)((char *)this + 8 * (*(_DWORD *)(v7 + 8) & 0x1F)); ; i = (__int64 *)(v10 + 40) )
      {
        v10 = *i;
        if ( !*i )
          break;
        if ( v10 == v7 )
        {
          *i = *(_QWORD *)(v7 + 40);
          *(_QWORD *)(v7 + 40) = 0;
          break;
        }
      }
      if ( v8 )
      {
        *(_QWORD *)(v7 + 24) = v8;
        *(_QWORD *)(v8 + 32) = v7;
      }
      else
      {
        v2 = v7;
      }
      *(_DWORD *)(v7 + 16) = 0;
      if ( !*v5 )
        goto LABEL_13;
      v6 = *v5;
    }
    v11 = -10000 * (*((_DWORD *)v6 + 12) - TickCount + 2000);
    pftDueTime.dwHighDateTime = (-10000LL * (unsigned __int64)(*((_DWORD *)v6 + 12) - TickCount + 2000)) >> 32;
    pftDueTime.dwLowDateTime = v11;
    SetThreadpoolTimer(*((PTP_TIMER *)this + 39), &pftDueTime, 0, 0x1F4u);
  }
LABEL_13:
  LeaveCriticalSection(v3);
  if ( v2 )
  {
    do
    {
      v12 = *(_QWORD *)(v2 + 32);
      (**(void (__fastcall ***)(__int64, __int64))v2)(v2, 1);
      v2 = v12;
    }
    while ( v12 );
  }
}

```

## disassembly

```asm
0x18006cd08  mov     [rsp+arg_8], rbx
0x18006cd0d  mov     [rsp+arg_10], rbp
0x18006cd12  push    rsi
0x18006cd13  push    rdi
0x18006cd14  push    r14
0x18006cd16  sub     rsp, 20h
0x18006cd1a  mov     rsi, rcx
0x18006cd1d  xor     edi, edi
0x18006cd1f  lea     rbx, [rcx+100h]
0x18006cd26  mov     rcx, rbx; lpCriticalSection
0x18006cd29  call    cs:__imp_EnterCriticalSection
0x18006cd2f  call    cs:__imp_GetTickCount
0x18006cd35  mov     ebp, eax
0x18006cd37  lea     r14, [rsi+150h]
0x18006cd3e  mov     r10, [r14]
0x18006cd41  test    r10, r10
0x18006cd44  jz      loc_18006CDF6
0x18006cd4a  xor     r11d, r11d
0x18006cd4d  mov     eax, ebp
0x18006cd4f  sub     eax, [r10+30h]
0x18006cd53  cmp     eax, 7D0h
0x18006cd58  jb      short loc_18006CDBA
0x18006cd5a  mov     rdx, r10; struct IGlyphFactory *
0x18006cd5d  mov     rcx, r14; this
0x18006cd60  call    ?Unlink@LinkedList@GlyphFactoryManager@@QEAAXPEAVIGlyphFactory@@@Z; GlyphFactoryManager::LinkedList::Unlink(IGlyphFactory *)
0x18006cd65  mov     r9d, [r10+8]
0x18006cd69  and     r9d, 1Fh
0x18006cd6d  lea     rcx, [rsi+r9*8]
0x18006cd71  mov     rax, [rcx]
0x18006cd74  test    rax, rax
0x18006cd77  jz      short loc_18006CD8D
0x18006cd79  cmp     rax, r10
0x18006cd7c  jnz     short loc_18006CDB4
0x18006cd7e  mov     rax, [r10+28h]
0x18006cd82  mov     [rcx], rax
0x18006cd85  mov     qword ptr [r10+28h], 0
0x18006cd8d  test    r11, r11
0x18006cd90  jz      loc_18006CE36
0x18006cd96  mov     [r10+18h], r11
0x18006cd9a  mov     [r11+20h], r10
0x18006cd9e  mov     dword ptr [r10+10h], 0
0x18006cda6  cmp     qword ptr [r14], 0
0x18006cdaa  jz      short loc_18006CDF6
0x18006cdac  mov     r11, r10
0x18006cdaf  mov     r10, [r14]
0x18006cdb2  jmp     short loc_18006CD4D
0x18006cdb4  lea     rcx, [rax+28h]
0x18006cdb8  jmp     short loc_18006CD71
0x18006cdba  mov     eax, [r10+30h]
0x18006cdbe  sub     eax, ebp
0x18006cdc0  add     eax, 7D0h
0x18006cdc5  imul    rax, 0FFFFFFFFFFFFD8F0h
0x18006cdcc  mov     rcx, rax
0x18006cdcf  shr     rcx, 20h
0x18006cdd3  mov     [rsp+38h+pftDueTime.dwHighDateTime], ecx
0x18006cdd7  mov     [rsp+38h+pftDueTime.dwLowDateTime], eax
0x18006cddb  mov     r9d, 1F4h; msWindowLength
0x18006cde1  xor     r8d, r8d; msPeriod
0x18006cde4  lea     rdx, [rsp+38h+pftDueTime]; pftDueTime
0x18006cde9  mov     rcx, [rsi+138h]; pti
0x18006cdf0  call    cs:__imp_SetThreadpoolTimer
0x18006cdf6  mov     rcx, rbx; lpCriticalSection
0x18006cdf9  call    cs:__imp_LeaveCriticalSection
0x18006cdff  test    rdi, rdi
0x18006ce02  jz      short loc_18006CE23
0x18006ce04  mov     rbx, [rdi+20h]
0x18006ce08  mov     rax, [rdi]
0x18006ce0b  mov     edx, 1
0x18006ce10  mov     rcx, rdi
0x18006ce13  mov     rax, [rax]
0x18006ce16  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006ce1b  mov     rdi, rbx
0x18006ce1e  test    rbx, rbx
0x18006ce21  jnz     short loc_18006CE04
0x18006ce23  mov     rbx, [rsp+38h+arg_8]
0x18006ce28  mov     rbp, [rsp+38h+arg_10]
0x18006ce2d  add     rsp, 20h
0x18006ce31  pop     r14
0x18006ce33  pop     rdi
0x18006ce34  pop     rsi
0x18006ce35  retn
0x18006ce36  mov     rdi, r10
0x18006ce39  jmp     loc_18006CD9E
```
