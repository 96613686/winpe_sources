# TOKEN_KEY::Initialize(void)

- ea: `0x180005680`
- end: `0x180005705`
- name: `?Initialize@TOKEN_KEY@@SAJXZ`
- size: `133`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x180003f30`

## callees

- `0x180005680`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800056aa`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800056aa`
- `iisutil!PuDbgPrint` at `0x1800056f3`
- `iisutil!PuDbgPrint` at `0x1800056f3`
- `CRYPTSP!CryptAcquireContextW` at `0x1800056a0`
- `CRYPTSP!CryptAcquireContextW` at `0x1800056a0`

## string_xrefs

- `0x1800056ec`: `servercommon\inetsrv\iis\iisrearc\iis70\auth_modules\common\iislogon_lib\iislogon.cxx`
- `0x1800056da`: `TOKEN_KEY::Initialize`

## pseudocode

```c
__int64 TOKEN_KEY::Initialize(void)
{
  signed int LastError; // eax
  unsigned int v1; // ebx

  if ( CryptAcquireContextW(&TOKEN_KEY::sm_hCryptProv, 0, 0, 0x18u, 0xF0000000) )
    return 0;
  LastError = GetLastError();
  v1 = LastError;
  if ( LastError > 0 )
    v1 = (unsigned __int16)LastError | 0x80070000;
  if ( (g_dwDebugFlags & 3) != 0 )
    PuDbgPrint(
      g_pDebug,
      "servercommon\\inetsrv\\iis\\iisrearc\\iis70\\auth_modules\\common\\iislogon_lib\\iislogon.cxx",
      982,
      "TOKEN_KEY::Initialize",
      "CryptAcquireContext() failed. hr = 0x%x\n",
      v1);
  return v1;
}

```

## disassembly

```asm
0x180005680  push    rbx
0x180005682  sub     rsp, 30h
0x180005686  mov     r9d, 18h; dwProvType
0x18000568c  mov     [rsp+38h+dwFlags], 0F0000000h; dwFlags
0x180005694  xor     r8d, r8d; szProvider
0x180005697  lea     rcx, ?sm_hCryptProv@TOKEN_KEY@@0_KA; phProv
0x18000569e  xor     edx, edx; szContainer
0x1800056a0  call    cs:__imp_CryptAcquireContextW
0x1800056a6  test    eax, eax
0x1800056a8  jnz     short loc_1800056FD
0x1800056aa  call    cs:__imp_GetLastError
0x1800056b0  mov     ebx, eax
0x1800056b2  test    eax, eax
0x1800056b4  jle     short loc_1800056BF
0x1800056b6  movzx   ebx, ax
0x1800056b9  or      ebx, 80070000h
0x1800056bf  test    byte ptr cs:g_dwDebugFlags, 3
0x1800056c6  jz      short loc_1800056F9
0x1800056c8  mov     rcx, cs:g_pDebug
0x1800056cf  lea     rax, aCryptacquireco; "CryptAcquireContext() failed. hr = 0x%x"...
0x1800056d6  mov     [rsp+38h+var_10], ebx
0x1800056da  lea     r9, aTokenKeyInitia; "TOKEN_KEY::Initialize"
0x1800056e1  mov     r8d, 3D6h
0x1800056e7  mov     qword ptr [rsp+38h+dwFlags], rax
0x1800056ec  lea     rdx, aServercommonIn; "servercommon\\inetsrv\\iis\\iisrearc\\i"...
0x1800056f3  call    cs:__imp_PuDbgPrint
0x1800056f9  mov     eax, ebx
0x1800056fb  jmp     short loc_1800056FF
0x1800056fd  xor     eax, eax
0x1800056ff  add     rsp, 30h
0x180005703  pop     rbx
0x180005704  retn
```
