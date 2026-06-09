# SSPI_USER_CONTEXT::Create(SSPI_SECURITY_CONTEXT *,char *)

- ea: `0x180007b38`
- end: `0x180007ce1`
- name: `?Create@SSPI_USER_CONTEXT@@QEAAJPEAVSSPI_SECURITY_CONTEXT@@PEAD@Z`
- size: `425`
- prototype: `int __fastcall(SSPI_USER_CONTEXT *this, struct _SecHandle *, char *)`
- caller_count: `1`
- callee_count: `1`
- tags: `file_ops, authz_impersonation, broker_com_uri`

## callers

- `0x1800021f0`

## callees

- `0x180007b38`

## import_xrefs

- `SspiCli!QuerySecurityContextToken` at `0x180007b80`
- `SspiCli!QuerySecurityContextToken` at `0x180007b80`
- `SspiCli!QueryContextAttributesA` at `0x180007c77`
- `SspiCli!QueryContextAttributesA` at `0x180007c77`
- `SspiCli!FreeContextBuffer` at `0x180007c60`
- `SspiCli!FreeContextBuffer` at `0x180007cb1`
- `SspiCli!FreeContextBuffer` at `0x180007c60`
- `SspiCli!FreeContextBuffer` at `0x180007cb1`
- `SspiCli!QueryContextAttributesW` at `0x180007bf8`
- `SspiCli!QueryContextAttributesW` at `0x180007bf8`
- `iisutil!?CopyA@STRU@@QEAAJPEBD@Z` at `0x180007cc5`
- `iisutil!?CopyA@STRU@@QEAAJPEBD@Z` at `0x180007cc5`
- `iisutil!PuDbgPrint` at `0x180007bc1`
- `iisutil!PuDbgPrint` at `0x180007c38`
- `iisutil!PuDbgPrint` at `0x180007bc1`
- `iisutil!PuDbgPrint` at `0x180007c38`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x180007c53`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x180007c53`
- `iisutil!DisableTokenBackupPrivilege` at `0x180007bd4`
- `iisutil!DisableTokenBackupPrivilege` at `0x180007bd4`
- `iisutil!AdjustTokenIntegrityLevel` at `0x180007bdd`
- `iisutil!AdjustTokenIntegrityLevel` at `0x180007bdd`
- `iisutil!?Copy@STRA@@QEAAJPEBD@Z` at `0x180007ca4`
- `iisutil!?Copy@STRA@@QEAAJPEBD@Z` at `0x180007ca4`

## string_xrefs

- `0x180007bb4`: `servercommon\inetsrv\iis\iisrearc\iis70\auth_modules\common\sspi_lib\sspi_lib.cxx`
- `0x180007c2c`: `servercommon\inetsrv\iis\iisrearc\iis70\auth_modules\common\sspi_lib\sspi_lib.cxx`
- `0x180007b96`: `Error QuerySecurityContextToken, hr = 0x%x.\n`
- `0x180007ba6`: `SSPI_USER_CONTEXT::Create`
- `0x180007c25`: `SSPI_USER_CONTEXT::Create`

## pseudocode

```c
int __fastcall SSPI_USER_CONTEXT::Create(SSPI_USER_CONTEXT *this, struct _SecHandle *a2, char *a3)
{
  int result; // eax
  struct _SecHandle *v6; // rsi
  void **v7; // rbx
  SECURITY_STATUS v8; // ebx
  __int64 v9; // r8
  int v10; // eax
  int v11; // ecx
  unsigned __int16 *pBuffer; // [rsp+58h] [rbp+10h] BYREF
  PVOID pvContextBuffer; // [rsp+68h] [rbp+20h] BYREF

  pBuffer = 0;
  pvContextBuffer = 0;
  if ( !a2 )
    return -2147024809;
  v6 = a2 + 2;
  *((_QWORD *)this + 35) = a2;
  v7 = (void **)((char *)this + 16);
  if ( QuerySecurityContextToken(a2 + 2, (void **)this + 2) == -2146893055 )
  {
    if ( (g_dwDebugFlags & 3) != 0 )
      PuDbgPrint(
        g_pDebug,
        "servercommon\\inetsrv\\iis\\iisrearc\\iis70\\auth_modules\\common\\sspi_lib\\sspi_lib.cxx",
        631,
        "SSPI_USER_CONTEXT::Create",
        "Error QuerySecurityContextToken, hr = 0x%x.\n",
        -2146893055);
    return -2146893055;
  }
  DisableTokenBackupPrivilege(*v7);
  result = AdjustTokenIntegrityLevel(*v7);
  if ( result < 0 )
    return result;
  v8 = QueryContextAttributesW(v6, 1u, &pBuffer);
  if ( v8 < 0 )
  {
    if ( (g_dwDebugFlags & 3) == 0 )
      return v8;
    v9 = 663;
LABEL_11:
    PuDbgPrint(
      g_pDebug,
      "servercommon\\inetsrv\\iis\\iisrearc\\iis70\\auth_modules\\common\\sspi_lib\\sspi_lib.cxx",
      v9,
      "SSPI_USER_CONTEXT::Create",
      "QueryContextAttributes() failed with ss = 0x%x.\n",
      v8);
    return v8;
  }
  if ( pBuffer )
  {
    v8 = STRU::Copy((SSPI_USER_CONTEXT *)((char *)this + 32), pBuffer);
    FreeContextBuffer(pBuffer);
    if ( v8 < 0 )
      return v8;
  }
  v8 = QueryContextAttributesA(v6, 0xAu, &pvContextBuffer);
  if ( v8 < 0 )
  {
    if ( (g_dwDebugFlags & 3) == 0 )
      return v8;
    v9 = 698;
    goto LABEL_11;
  }
  v8 = STRA::Copy((SSPI_USER_CONTEXT *)((char *)this + 88), *((const char **)pvContextBuffer + 2));
  FreeContextBuffer(pvContextBuffer);
  if ( v8 < 0 )
    return v8;
  v10 = STRU::CopyA((SSPI_USER_CONTEXT *)((char *)this + 144), a3);
  v11 = 0;
  if ( v10 < 0 )
    return v10;
  return v11;
}

```

## disassembly

```asm
0x180007b38  mov     [rsp+arg_0], rbx
0x180007b3d  push    rbp
0x180007b3e  push    rsi
0x180007b3f  push    rdi
0x180007b40  sub     rsp, 30h
0x180007b44  mov     [rsp+48h+pBuffer], 0
0x180007b4d  mov     rbp, r8
0x180007b50  mov     [rsp+48h+pvContextBuffer], 0
0x180007b59  mov     rdi, rcx
0x180007b5c  test    rdx, rdx
0x180007b5f  jnz     short loc_180007B6B
0x180007b61  mov     eax, 80070057h
0x180007b66  jmp     loc_180007CD4
0x180007b6b  lea     rsi, [rdx+20h]
0x180007b6f  mov     [rcx+118h], rdx
0x180007b76  lea     rbx, [rcx+10h]
0x180007b7a  mov     rcx, rsi; phContext
0x180007b7d  mov     rdx, rbx; Token
0x180007b80  call    cs:__imp_QuerySecurityContextToken
0x180007b86  cmp     eax, 80090301h
0x180007b8b  jnz     short loc_180007BD1
0x180007b8d  test    byte ptr cs:g_dwDebugFlags, 3
0x180007b94  jz      short loc_180007BC7
0x180007b96  lea     rcx, aErrorQuerysecu; "Error QuerySecurityContextToken, hr = 0"...
0x180007b9d  mov     [rsp+48h+var_20], eax
0x180007ba1  mov     [rsp+48h+var_28], rcx
0x180007ba6  lea     r9, aSspiUserContex; "SSPI_USER_CONTEXT::Create"
0x180007bad  mov     rcx, cs:g_pDebug
0x180007bb4  lea     rdx, aServercommonIn_0; "servercommon\\inetsrv\\iis\\iisrearc\\i"...
0x180007bbb  mov     r8d, 277h
0x180007bc1  call    cs:__imp_PuDbgPrint
0x180007bc7  mov     eax, 80090301h
0x180007bcc  jmp     loc_180007CD4
0x180007bd1  mov     rcx, [rbx]
0x180007bd4  call    cs:__imp_?DisableTokenBackupPrivilege@@YAXPEAX@Z; DisableTokenBackupPrivilege(void *)
0x180007bda  mov     rcx, [rbx]
0x180007bdd  call    cs:__imp_?AdjustTokenIntegrityLevel@@YAJPEAX@Z; AdjustTokenIntegrityLevel(void *)
0x180007be3  test    eax, eax
0x180007be5  js      loc_180007CD4
0x180007beb  lea     r8, [rsp+48h+pBuffer]; pBuffer
0x180007bf0  mov     edx, 1; ulAttribute
0x180007bf5  mov     rcx, rsi; phContext
0x180007bf8  call    cs:__imp_QueryContextAttributesW
0x180007bfe  mov     ebx, eax
0x180007c00  test    eax, eax
0x180007c02  jns     short loc_180007C45
0x180007c04  test    byte ptr cs:g_dwDebugFlags, 3
0x180007c0b  jz      short loc_180007C3E
0x180007c0d  mov     r8d, 297h
0x180007c13  mov     rcx, cs:g_pDebug
0x180007c1a  lea     rax, aQuerycontextat; "QueryContextAttributes() failed with ss"...
0x180007c21  mov     [rsp+48h+var_20], ebx
0x180007c25  lea     r9, aSspiUserContex; "SSPI_USER_CONTEXT::Create"
0x180007c2c  lea     rdx, aServercommonIn_0; "servercommon\\inetsrv\\iis\\iisrearc\\i"...
0x180007c33  mov     [rsp+48h+var_28], rax
0x180007c38  call    cs:__imp_PuDbgPrint
0x180007c3e  mov     eax, ebx
0x180007c40  jmp     loc_180007CD4
0x180007c45  mov     rdx, [rsp+48h+pBuffer]
0x180007c4a  test    rdx, rdx
0x180007c4d  jz      short loc_180007C6A
0x180007c4f  lea     rcx, [rdi+20h]
0x180007c53  call    cs:__imp_?Copy@STRU@@QEAAJPEBG@Z; STRU::Copy(ushort const *)
0x180007c59  mov     rcx, [rsp+48h+pBuffer]; pvContextBuffer
0x180007c5e  mov     ebx, eax
0x180007c60  call    cs:__imp_FreeContextBuffer
0x180007c66  test    ebx, ebx
0x180007c68  js      short loc_180007C3E
0x180007c6a  lea     r8, [rsp+48h+pvContextBuffer]; pBuffer
0x180007c6f  mov     edx, 0Ah; ulAttribute
0x180007c74  mov     rcx, rsi; phContext
0x180007c77  call    cs:__imp_QueryContextAttributesA
0x180007c7d  mov     ebx, eax
0x180007c7f  test    eax, eax
0x180007c81  jns     short loc_180007C97
0x180007c83  test    byte ptr cs:g_dwDebugFlags, 3
0x180007c8a  jz      short loc_180007C3E
0x180007c8c  mov     r8d, 2BAh
0x180007c92  jmp     loc_180007C13
0x180007c97  mov     rdx, [rsp+48h+pvContextBuffer]
0x180007c9c  lea     rcx, [rdi+58h]
0x180007ca0  mov     rdx, [rdx+10h]
0x180007ca4  call    cs:__imp_?Copy@STRA@@QEAAJPEBD@Z; STRA::Copy(char const *)
0x180007caa  mov     rcx, [rsp+48h+pvContextBuffer]; pvContextBuffer
0x180007caf  mov     ebx, eax
0x180007cb1  call    cs:__imp_FreeContextBuffer
0x180007cb7  test    ebx, ebx
0x180007cb9  js      short loc_180007C3E
0x180007cbb  lea     rcx, [rdi+90h]
0x180007cc2  mov     rdx, rbp
0x180007cc5  call    cs:__imp_?CopyA@STRU@@QEAAJPEBD@Z; STRU::CopyA(char const *)
0x180007ccb  xor     ecx, ecx
0x180007ccd  test    eax, eax
0x180007ccf  cmovs   ecx, eax
0x180007cd2  mov     eax, ecx
0x180007cd4  mov     rbx, [rsp+48h+arg_0]
0x180007cd9  add     rsp, 30h
0x180007cdd  pop     rdi
0x180007cde  pop     rsi
0x180007cdf  pop     rbp
0x180007ce0  retn
```
