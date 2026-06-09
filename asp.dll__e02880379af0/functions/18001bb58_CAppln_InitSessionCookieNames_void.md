# CAppln::InitSessionCookieNames(void)

- ea: `0x18001bb58`
- end: `0x18001bbf7`
- name: `?InitSessionCookieNames@CAppln@@AEAAXXZ`
- size: `159`
- prototype: `void __fastcall(CAppln *__hidden this)`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation`

## callers

- `0x1800054e8`

## callees

- `0x18001bc00`

## import_xrefs

- `msvcrt!time` at `0x18001bb92`
- `msvcrt!time` at `0x18001bb92`
- `KERNEL32!GetTickCount` at `0x18001bb98`
- `KERNEL32!GetTickCount` at `0x18001bb98`
- `KERNEL32!GetCurrentProcessId` at `0x18001bb6a`
- `KERNEL32!GetCurrentProcessId` at `0x18001bb6a`

## pseudocode

```c
void __fastcall CAppln::InitSessionCookieNames(CAppln *this)
{
  DWORD CurrentProcessId; // ebx
  unsigned int v3; // edi
  CAppln *v4; // rcx
  unsigned int v5; // ebx
  CAppln *v6; // rcx
  time_t Time; // [rsp+40h] [rbp+8h] BYREF

  CurrentProcessId = GetCurrentProcessId();
  Time = 0;
  v3 = 2 * _InterlockedIncrement(&dword_180079B68);
  time(&Time);
  v4 = (CAppln *)((1000 * (_DWORD)Time - GetTickCount()) >> 12);
  v5 = ((unsigned __int16)v4 << 8) + CurrentProcessId;
  CAppln::EncodeCookie(v4, (char *)this + 400, v5, v3, 0);
  CAppln::EncodeCookie(v6, (char *)this + 421, v5, v3, 1);
}

```

## disassembly

```asm
0x18001bb58  mov     [rsp+arg_8], rbx
0x18001bb5d  mov     [rsp+arg_10], rsi
0x18001bb62  push    rdi
0x18001bb63  sub     rsp, 30h
0x18001bb67  mov     rsi, rcx
0x18001bb6a  call    cs:__imp_GetCurrentProcessId
0x18001bb70  mov     ebx, eax
0x18001bb72  mov     edx, 1
0x18001bb77  lock xadd cs:dword_180079B68, edx
0x18001bb7f  inc     edx
0x18001bb81  mov     [rsp+38h+Time], 0
0x18001bb8a  lea     rcx, [rsp+38h+Time]; Time
0x18001bb8f  lea     edi, [rdx+rdx]
0x18001bb92  call    cs:__imp_time
0x18001bb98  call    cs:__imp_GetTickCount
0x18001bb9e  imul    ecx, dword ptr [rsp+38h+Time], 3E8h
0x18001bba6  lea     rdx, [rsi+190h]; char *
0x18001bbad  mov     r9d, edi; unsigned int
0x18001bbb0  mov     [rsp+38h+var_18], 0; int
0x18001bbb8  sub     ecx, eax
0x18001bbba  shr     ecx, 0Ch; this
0x18001bbbd  movzx   eax, cx
0x18001bbc0  shl     eax, 8
0x18001bbc3  add     ebx, eax
0x18001bbc5  mov     r8d, ebx; unsigned int
0x18001bbc8  call    ?EncodeCookie@CAppln@@AEAAXPEADKKH@Z; CAppln::EncodeCookie(char *,ulong,ulong,int)
0x18001bbcd  lea     rdx, [rsi+1A5h]; char *
0x18001bbd4  mov     [rsp+38h+var_18], 1; int
0x18001bbdc  mov     r9d, edi; unsigned int
0x18001bbdf  mov     r8d, ebx; unsigned int
0x18001bbe2  call    ?EncodeCookie@CAppln@@AEAAXPEADKKH@Z; CAppln::EncodeCookie(char *,ulong,ulong,int)
0x18001bbe7  mov     rbx, [rsp+38h+arg_8]
0x18001bbec  mov     rsi, [rsp+38h+arg_10]
0x18001bbf1  add     rsp, 30h
0x18001bbf5  pop     rdi
0x18001bbf6  retn
```
