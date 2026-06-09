# ShieldProvider::CAutoSetThreadLowPriority::CAutoSetThreadLowPriority(void)

- ea: `0x1800117cc`
- end: `0x18001183d`
- name: `??0CAutoSetThreadLowPriority@ShieldProvider@@QEAA@XZ`
- size: `113`
- prototype: `__int64 __fastcall(ShieldProvider::CAutoSetThreadLowPriority *__hidden this)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x180012c40`

## callees

- `0x18000d7fc`
- `0x1800117cc`

## import_xrefs

- `KERNEL32!GetLastError` at `0x1800117ed`
- `KERNEL32!GetLastError` at `0x1800117ed`
- `KERNEL32!SetThreadPriority` at `0x1800117e3`
- `KERNEL32!SetThreadPriority` at `0x1800117e3`
- `KERNEL32!GetCurrentThread` at `0x1800117d5`
- `KERNEL32!GetCurrentThread` at `0x1800117d5`

## pseudocode

```c
ShieldProvider::CAutoSetThreadLowPriority *__fastcall ShieldProvider::CAutoSetThreadLowPriority::CAutoSetThreadLowPriority(
        ShieldProvider::CAutoSetThreadLowPriority *this)
{
  HANDLE CurrentThread; // rax
  signed int LastError; // eax
  bool v4; // sf

  CurrentThread = GetCurrentThread();
  if ( !SetThreadPriority(CurrentThread, 0x10000) )
  {
    LastError = GetLastError();
    v4 = LastError < 0;
    if ( LastError > 0 )
    {
      LastError = (unsigned __int16)LastError | 0x80070000;
      v4 = LastError < 0;
    }
    if ( v4 && WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        10,
        WPP_c15b3361942b3cf72eefef62f859076e_Traceguids,
        (unsigned int)LastError);
  }
  return this;
}

```

## disassembly

```asm
0x1800117cc  push    rbx
0x1800117ce  sub     rsp, 20h
0x1800117d2  mov     rbx, rcx
0x1800117d5  call    cs:__imp_GetCurrentThread
0x1800117db  mov     rcx, rax; hThread
0x1800117de  mov     edx, 10000h; nPriority
0x1800117e3  call    cs:__imp_SetThreadPriority
0x1800117e9  test    eax, eax
0x1800117eb  jnz     short loc_180011834
0x1800117ed  call    cs:__imp_GetLastError
0x1800117f3  test    eax, eax
0x1800117f5  jle     short loc_180011801
0x1800117f7  movzx   eax, ax
0x1800117fa  or      eax, 80070000h
0x1800117ff  test    eax, eax
0x180011801  jns     short loc_180011834
0x180011803  mov     rcx, cs:WPP_GLOBAL_Control
0x18001180a  lea     rdx, WPP_GLOBAL_Control
0x180011811  cmp     rcx, rdx
0x180011814  jz      short loc_180011834
0x180011816  test    byte ptr [rcx+1Ch], 1
0x18001181a  jz      short loc_180011834
0x18001181c  mov     rcx, [rcx+10h]
0x180011820  lea     r8, WPP_c15b3361942b3cf72eefef62f859076e_Traceguids
0x180011827  mov     edx, 0Ah
0x18001182c  mov     r9d, eax
0x18001182f  call    WPP_SF_d
0x180011834  mov     rax, rbx
0x180011837  add     rsp, 20h
0x18001183b  pop     rbx
0x18001183c  retn
```
