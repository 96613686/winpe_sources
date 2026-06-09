# SSPI_USER_CONTEXT::Create(SSPI_SECURITY_CONTEXT *,char *)

- ea: `0x180005864`
- end: `0x180005a0d`
- name: `?Create@SSPI_USER_CONTEXT@@QEAAJPEAVSSPI_SECURITY_CONTEXT@@PEAD@Z`
- size: `425`
- prototype: `int __fastcall(SSPI_USER_CONTEXT *this, struct _SecHandle *, char *)`
- caller_count: `1`
- callee_count: `1`
- tags: `file_ops, authz_impersonation, broker_com_uri`

## callers

- `0x180001e00`

## callees

- `0x180005864`

## import_xrefs

- `SspiCli!QueryContextAttributesW` at `0x180005924`
- `SspiCli!QueryContextAttributesW` at `0x180005924`
- `SspiCli!QuerySecurityContextToken` at `0x1800058ac`
- `SspiCli!QuerySecurityContextToken` at `0x1800058ac`
- `SspiCli!QueryContextAttributesA` at `0x1800059a3`
- `SspiCli!QueryContextAttributesA` at `0x1800059a3`
- `SspiCli!FreeContextBuffer` at `0x18000598c`
- `SspiCli!FreeContextBuffer` at `0x1800059dd`
- `SspiCli!FreeContextBuffer` at `0x18000598c`
- `SspiCli!FreeContextBuffer` at `0x1800059dd`
- `iisutil!AdjustTokenIntegrityLevel` at `0x180005909`
- `iisutil!AdjustTokenIntegrityLevel` at `0x180005909`
- `iisutil!DisableTokenBackupPrivilege` at `0x180005900`
- `iisutil!DisableTokenBackupPrivilege` at `0x180005900`
- `iisutil!?CopyA@STRU@@QEAAJPEBD@Z` at `0x1800059f1`
- `iisutil!?CopyA@STRU@@QEAAJPEBD@Z` at `0x1800059f1`
- `iisutil!PuDbgPrint` at `0x1800058ed`
- `iisutil!PuDbgPrint` at `0x180005964`
- `iisutil!PuDbgPrint` at `0x1800058ed`
- `iisutil!PuDbgPrint` at `0x180005964`
- `iisutil!?Copy@STRA@@QEAAJPEBD@Z` at `0x1800059d0`
- `iisutil!?Copy@STRA@@QEAAJPEBD@Z` at `0x1800059d0`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x18000597f`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x18000597f`

## string_xrefs

- `0x1800058e0`: `servercommon\inetsrv\iis\iisrearc\iis70\auth_modules\common\sspi_lib\sspi_lib.cxx`
- `0x180005958`: `servercommon\inetsrv\iis\iisrearc\iis70\auth_modules\common\sspi_lib\sspi_lib.cxx`
- `0x1800058c2`: `Error QuerySecurityContextToken, hr = 0x%x.\n`
- `0x1800058d2`: `SSPI_USER_CONTEXT::Create`
- `0x180005951`: `SSPI_USER_CONTEXT::Create`

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
0x180005864  mov     [rsp+arg_0], rbx
0x180005869  push    rbp
0x18000586a  push    rsi
0x18000586b  push    rdi
0x18000586c  sub     rsp, 30h
0x180005870  mov     [rsp+48h+pBuffer], 0
0x180005879  mov     rbp, r8
0x18000587c  mov     [rsp+48h+pvContextBuffer], 0
0x180005885  mov     rdi, rcx
0x180005888  test    rdx, rdx
0x18000588b  jnz     short loc_180005897
0x18000588d  mov     eax, 80070057h
0x180005892  jmp     loc_180005A00
0x180005897  lea     rsi, [rdx+20h]
0x18000589b  mov     [rcx+118h], rdx
0x1800058a2  lea     rbx, [rcx+10h]
0x1800058a6  mov     rcx, rsi; phContext
0x1800058a9  mov     rdx, rbx; Token
0x1800058ac  call    cs:__imp_QuerySecurityContextToken
0x1800058b2  cmp     eax, 80090301h
0x1800058b7  jnz     short loc_1800058FD
0x1800058b9  test    byte ptr cs:g_dwDebugFlags, 3
0x1800058c0  jz      short loc_1800058F3
0x1800058c2  lea     rcx, aErrorQuerysecu; "Error QuerySecurityContextToken, hr = 0"...
0x1800058c9  mov     [rsp+48h+var_20], eax
0x1800058cd  mov     [rsp+48h+var_28], rcx
0x1800058d2  lea     r9, aSspiUserContex; "SSPI_USER_CONTEXT::Create"
0x1800058d9  mov     rcx, cs:g_pDebug
0x1800058e0  lea     rdx, aServercommonIn_0; "servercommon\\inetsrv\\iis\\iisrearc\\i"...
0x1800058e7  mov     r8d, 277h
0x1800058ed  call    cs:__imp_PuDbgPrint
0x1800058f3  mov     eax, 80090301h
0x1800058f8  jmp     loc_180005A00
0x1800058fd  mov     rcx, [rbx]
0x180005900  call    cs:__imp_?DisableTokenBackupPrivilege@@YAXPEAX@Z; DisableTokenBackupPrivilege(void *)
0x180005906  mov     rcx, [rbx]
0x180005909  call    cs:__imp_?AdjustTokenIntegrityLevel@@YAJPEAX@Z; AdjustTokenIntegrityLevel(void *)
0x18000590f  test    eax, eax
0x180005911  js      loc_180005A00
0x180005917  lea     r8, [rsp+48h+pBuffer]; pBuffer
0x18000591c  mov     edx, 1; ulAttribute
0x180005921  mov     rcx, rsi; phContext
0x180005924  call    cs:__imp_QueryContextAttributesW
0x18000592a  mov     ebx, eax
0x18000592c  test    eax, eax
0x18000592e  jns     short loc_180005971
0x180005930  test    byte ptr cs:g_dwDebugFlags, 3
0x180005937  jz      short loc_18000596A
0x180005939  mov     r8d, 297h
0x18000593f  mov     rcx, cs:g_pDebug
0x180005946  lea     rax, aQuerycontextat; "QueryContextAttributes() failed with ss"...
0x18000594d  mov     [rsp+48h+var_20], ebx
0x180005951  lea     r9, aSspiUserContex; "SSPI_USER_CONTEXT::Create"
0x180005958  lea     rdx, aServercommonIn_0; "servercommon\\inetsrv\\iis\\iisrearc\\i"...
0x18000595f  mov     [rsp+48h+var_28], rax
0x180005964  call    cs:__imp_PuDbgPrint
0x18000596a  mov     eax, ebx
0x18000596c  jmp     loc_180005A00
0x180005971  mov     rdx, [rsp+48h+pBuffer]
0x180005976  test    rdx, rdx
0x180005979  jz      short loc_180005996
0x18000597b  lea     rcx, [rdi+20h]
0x18000597f  call    cs:__imp_?Copy@STRU@@QEAAJPEBG@Z; STRU::Copy(ushort const *)
0x180005985  mov     rcx, [rsp+48h+pBuffer]; pvContextBuffer
0x18000598a  mov     ebx, eax
0x18000598c  call    cs:__imp_FreeContextBuffer
0x180005992  test    ebx, ebx
0x180005994  js      short loc_18000596A
0x180005996  lea     r8, [rsp+48h+pvContextBuffer]; pBuffer
0x18000599b  mov     edx, 0Ah; ulAttribute
0x1800059a0  mov     rcx, rsi; phContext
0x1800059a3  call    cs:__imp_QueryContextAttributesA
0x1800059a9  mov     ebx, eax
0x1800059ab  test    eax, eax
0x1800059ad  jns     short loc_1800059C3
0x1800059af  test    byte ptr cs:g_dwDebugFlags, 3
0x1800059b6  jz      short loc_18000596A
0x1800059b8  mov     r8d, 2BAh
0x1800059be  jmp     loc_18000593F
0x1800059c3  mov     rdx, [rsp+48h+pvContextBuffer]
0x1800059c8  lea     rcx, [rdi+58h]
0x1800059cc  mov     rdx, [rdx+10h]
0x1800059d0  call    cs:__imp_?Copy@STRA@@QEAAJPEBD@Z; STRA::Copy(char const *)
0x1800059d6  mov     rcx, [rsp+48h+pvContextBuffer]; pvContextBuffer
0x1800059db  mov     ebx, eax
0x1800059dd  call    cs:__imp_FreeContextBuffer
0x1800059e3  test    ebx, ebx
0x1800059e5  js      short loc_18000596A
0x1800059e7  lea     rcx, [rdi+90h]
0x1800059ee  mov     rdx, rbp
0x1800059f1  call    cs:__imp_?CopyA@STRU@@QEAAJPEBD@Z; STRU::CopyA(char const *)
0x1800059f7  xor     ecx, ecx
0x1800059f9  test    eax, eax
0x1800059fb  cmovs   ecx, eax
0x1800059fe  mov     eax, ecx
0x180005a00  mov     rbx, [rsp+48h+arg_0]
0x180005a05  add     rsp, 30h
0x180005a09  pop     rdi
0x180005a0a  pop     rsi
0x180005a0b  pop     rbp
0x180005a0c  retn
```
