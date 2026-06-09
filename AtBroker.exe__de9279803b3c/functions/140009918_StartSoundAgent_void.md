# StartSoundAgent(void)

- ea: `0x140009918`
- end: `0x1400099ef`
- name: `?StartSoundAgent@@YAHXZ`
- size: `215`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting, service_task`

## callers

- `0x14000b250`

## callees

- `0x140009918`
- `0x140015b00`

## import_xrefs

- `KERNEL32!ExpandEnvironmentStringsW` at `0x140009985`
- `KERNEL32!ExpandEnvironmentStringsW` at `0x140009985`
- `msvcrt!malloc` at `0x140009969`
- `msvcrt!malloc` at `0x140009969`
- `msvcrt!free` at `0x1400099c9`
- `msvcrt!free` at `0x1400099c9`
- `SHELL32!ShellExecuteW` at `0x1400099b8`
- `SHELL32!ShellExecuteW` at `0x1400099b8`

## string_xrefs

- `0x140009934`: `%SystemRoot%\System32\Sethc.exe`
- `0x14000999c`: `/AccessibilitySoundAgent`

## pseudocode

```c
__int64 StartSoundAgent(void)
{
  WCHAR *v0; // rax
  WCHAR *v1; // rdi
  unsigned int v2; // ebx
  WCHAR Src[32]; // [rsp+30h] [rbp-58h] BYREF

  wcscpy(Src, L"%SystemRoot%\\System32\\Sethc.exe");
  v0 = (WCHAR *)malloc(0x208u);
  v1 = v0;
  if ( !v0
    || ExpandEnvironmentStringsW(Src, v0, 0x104u) - 1 > 0x103
    || (v2 = 1, (__int64)ShellExecuteW(0, 0, v1, L"/AccessibilitySoundAgent", 0, 0) <= 32) )
  {
    v2 = 0;
  }
  free(v1);
  return v2;
}

```

## disassembly

```asm
0x140009918  mov     [rsp+arg_0], rbx
0x14000991d  push    rdi
0x14000991e  sub     rsp, 80h
0x140009925  mov     rax, cs:__security_cookie
0x14000992c  xor     rax, rsp
0x14000992f  mov     [rsp+88h+var_18], rax
0x140009934  movaps  xmm0, xmmword ptr cs:aSystemrootSyst; "%SystemRoot%\\System32\\Sethc.exe"
0x14000993b  mov     ecx, 208h; Size
0x140009940  movaps  xmm1, xmmword ptr cs:aSystemrootSyst+10h; "oot%\\System32\\Sethc.exe"
0x140009947  movaps  xmmword ptr [rsp+88h+Src], xmm0
0x14000994c  movaps  xmm0, xmmword ptr cs:aSystemrootSyst+20h; "tem32\\Sethc.exe"
0x140009953  movaps  [rsp+88h+var_48], xmm1
0x140009958  movaps  xmm1, xmmword ptr cs:aSystemrootSyst+30h; "thc.exe"
0x14000995f  movaps  [rsp+88h+var_38], xmm0
0x140009964  movaps  [rsp+88h+var_28], xmm1
0x140009969  call    cs:__imp_malloc
0x14000996f  mov     rdi, rax
0x140009972  test    rax, rax
0x140009975  jz      short loc_1400099C4
0x140009977  mov     r8d, 104h; nSize
0x14000997d  lea     rcx, [rsp+88h+Src]; lpSrc
0x140009982  mov     rdx, rax; lpDst
0x140009985  call    cs:__imp_ExpandEnvironmentStringsW
0x14000998b  dec     eax
0x14000998d  cmp     eax, 103h
0x140009992  ja      short loc_1400099C4
0x140009994  mov     [rsp+88h+nShowCmd], 0; nShowCmd
0x14000999c  lea     r9, aAccessibilitys; "/AccessibilitySoundAgent"
0x1400099a3  mov     r8, rdi; lpFile
0x1400099a6  mov     [rsp+88h+lpDirectory], 0; lpDirectory
0x1400099af  xor     edx, edx; lpOperation
0x1400099b1  xor     ecx, ecx; hwnd
0x1400099b3  mov     ebx, 1
0x1400099b8  call    cs:__imp_ShellExecuteW
0x1400099be  cmp     rax, 20h ; ' '
0x1400099c2  jg      short loc_1400099C6
0x1400099c4  xor     ebx, ebx
0x1400099c6  mov     rcx, rdi; Block
0x1400099c9  call    cs:__imp_free
0x1400099cf  mov     eax, ebx
0x1400099d1  mov     rcx, [rsp+88h+var_18]
0x1400099d6  xor     rcx, rsp; StackCookie
0x1400099d9  call    __security_check_cookie
0x1400099de  mov     rbx, [rsp+88h+arg_0]
0x1400099e6  add     rsp, 80h
0x1400099ed  pop     rdi
0x1400099ee  retn
```
