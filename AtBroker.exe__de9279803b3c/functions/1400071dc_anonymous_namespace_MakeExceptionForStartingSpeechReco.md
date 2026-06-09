# _anonymous_namespace_::MakeExceptionForStartingSpeechReco

- ea: `0x1400071dc`
- end: `0x1400072a2`
- name: `_anonymous_namespace_::MakeExceptionForStartingSpeechReco`
- size: `198`
- prototype: `HINSTANCE()`
- caller_count: `1`
- callee_count: `3`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x14000b250`

## callees

- `0x1400071dc`
- `0x140015ac2`
- `0x140015b00`

## import_xrefs

- `SHELL32!ShellExecuteW` at `0x140007284`
- `SHELL32!ShellExecuteW` at `0x140007284`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!SHExpandEnvironmentStringsW` at `0x140007256`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!SHExpandEnvironmentStringsW` at `0x140007256`

## string_xrefs

- `0x1400071f5`: `%SystemRoot%\Speech\Common\sapisvr.exe`

## pseudocode

```c
HINSTANCE anonymous_namespace_::MakeExceptionForStartingSpeechReco()
{
  HINSTANCE result; // rax
  _OWORD v1[3]; // [rsp+30h] [rbp-438h] BYREF
  _BYTE v2[30]; // [rsp+60h] [rbp-408h]
  _BYTE v3[450]; // [rsp+7Eh] [rbp-3EAh] BYREF
  WCHAR File[264]; // [rsp+240h] [rbp-228h] BYREF

  v1[0] = *(_OWORD *)L"%SystemRoot%\\Speech\\Common\\sapisvr.exe";
  v1[2] = *(_OWORD *)L"ech\\Common\\sapisvr.exe";
  v1[1] = *(_OWORD *)L"oot%\\Speech\\Common\\sapisvr.exe";
  *(_OWORD *)v2 = *(_OWORD *)L"on\\sapisvr.exe";
  *(_OWORD *)&v2[14] = *(_OWORD *)L"svr.exe";
  memset_0(v3, 0, 0x1BAu);
  result = (HINSTANCE)SHExpandEnvironmentStringsW(v1, File, 260);
  if ( (_DWORD)result )
    return ShellExecuteW(0, 0, File, L"-SpeechUX", 0, 1);
  return result;
}

```

## disassembly

```asm
0x1400071dc  sub     rsp, 468h
0x1400071e3  mov     rax, cs:__security_cookie
0x1400071ea  xor     rax, rsp
0x1400071ed  mov     [rsp+468h+var_18], rax
0x1400071f5  movaps  xmm0, xmmword ptr cs:aSystemrootSpee; "%SystemRoot%\\Speech\\Common\\sapisvr.e"...
0x1400071fc  lea     rcx, [rsp+468h+var_3EA]; void *
0x140007201  movaps  xmm1, xmmword ptr cs:aSystemrootSpee+10h; "oot%\\Speech\\Common\\sapisvr.exe"
0x140007208  xor     edx, edx; Val
0x14000720a  movaps  [rsp+468h+var_438], xmm0
0x14000720f  mov     r8d, 1BAh; Size
0x140007215  movaps  xmm0, xmmword ptr cs:aSystemrootSpee+20h; "ech\\Common\\sapisvr.exe"
0x14000721c  movaps  [rsp+468h+var_418], xmm0
0x140007221  movups  xmm0, xmmword ptr cs:aSystemrootSpee+3Eh; "svr.exe"
0x140007228  movaps  [rsp+468h+var_428], xmm1
0x14000722d  movaps  xmm1, xmmword ptr cs:aSystemrootSpee+30h; "on\\sapisvr.exe"
0x140007234  movaps  xmmword ptr [rsp+468h+var_408], xmm1
0x140007239  movups  xmmword ptr [rsp+468h+var_408+0Eh], xmm0
0x14000723e  call    memset_0
0x140007243  mov     r8d, 104h
0x140007249  lea     rdx, [rsp+468h+File]
0x140007251  lea     rcx, [rsp+468h+var_438]
0x140007256  call    cs:__imp_SHExpandEnvironmentStringsW
0x14000725c  test    eax, eax
0x14000725e  jz      short loc_14000728A
0x140007260  mov     [rsp+468h+nShowCmd], 1; nShowCmd
0x140007268  lea     r9, Parameters; "-SpeechUX"
0x14000726f  lea     r8, [rsp+468h+File]; lpFile
0x140007277  mov     [rsp+468h+lpDirectory], 0; lpDirectory
0x140007280  xor     edx, edx; lpOperation
0x140007282  xor     ecx, ecx; hwnd
0x140007284  call    cs:__imp_ShellExecuteW
0x14000728a  mov     rcx, [rsp+468h+var_18]
0x140007292  xor     rcx, rsp; StackCookie
0x140007295  call    __security_check_cookie
0x14000729a  add     rsp, 468h
0x1400072a1  retn
```
