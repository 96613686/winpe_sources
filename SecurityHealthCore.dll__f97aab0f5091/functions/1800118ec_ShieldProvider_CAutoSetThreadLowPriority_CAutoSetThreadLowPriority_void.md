# ShieldProvider::CAutoSetThreadLowPriority::~CAutoSetThreadLowPriority(void)

- ea: `0x1800118ec`
- end: `0x180011954`
- name: `??1CAutoSetThreadLowPriority@ShieldProvider@@QEAA@XZ`
- size: `104`
- prototype: `void __fastcall(ShieldProvider::CAutoSetThreadLowPriority *__hidden this)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x180012c40`

## callees

- `0x18000d7fc`
- `0x1800118ec`

## import_xrefs

- `KERNEL32!GetLastError` at `0x180011908`
- `KERNEL32!GetLastError` at `0x180011908`
- `KERNEL32!SetThreadPriority` at `0x1800118fe`
- `KERNEL32!SetThreadPriority` at `0x1800118fe`
- `KERNEL32!GetCurrentThread` at `0x1800118f0`
- `KERNEL32!GetCurrentThread` at `0x1800118f0`

## pseudocode

```c
void __fastcall ShieldProvider::CAutoSetThreadLowPriority::~CAutoSetThreadLowPriority(
        ShieldProvider::CAutoSetThreadLowPriority *this)
{
  HANDLE CurrentThread; // rax
  signed int LastError; // eax
  bool v3; // sf

  CurrentThread = GetCurrentThread();
  if ( !SetThreadPriority(CurrentThread, 0x20000) )
  {
    LastError = GetLastError();
    v3 = LastError < 0;
    if ( LastError > 0 )
    {
      LastError = (unsigned __int16)LastError | 0x80070000;
      v3 = LastError < 0;
    }
    if ( v3 && WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        11,
        WPP_c15b3361942b3cf72eefef62f859076e_Traceguids,
        (unsigned int)LastError);
  }
}

```

## disassembly

```asm
0x1800118ec  sub     rsp, 28h
0x1800118f0  call    cs:__imp_GetCurrentThread
0x1800118f6  mov     rcx, rax; hThread
0x1800118f9  mov     edx, 20000h; nPriority
0x1800118fe  call    cs:__imp_SetThreadPriority
0x180011904  test    eax, eax
0x180011906  jnz     short loc_18001194F
0x180011908  call    cs:__imp_GetLastError
0x18001190e  test    eax, eax
0x180011910  jle     short loc_18001191C
0x180011912  movzx   eax, ax
0x180011915  or      eax, 80070000h
0x18001191a  test    eax, eax
0x18001191c  jns     short loc_18001194F
0x18001191e  mov     rcx, cs:WPP_GLOBAL_Control
0x180011925  lea     rdx, WPP_GLOBAL_Control
0x18001192c  cmp     rcx, rdx
0x18001192f  jz      short loc_18001194F
0x180011931  test    byte ptr [rcx+1Ch], 1
0x180011935  jz      short loc_18001194F
0x180011937  mov     rcx, [rcx+10h]
0x18001193b  lea     r8, WPP_c15b3361942b3cf72eefef62f859076e_Traceguids
0x180011942  mov     edx, 0Bh
0x180011947  mov     r9d, eax
0x18001194a  call    WPP_SF_d
0x18001194f  add     rsp, 28h
0x180011953  retn
```
