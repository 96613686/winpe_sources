# TBGetKeyStorageLocation

- ea: `0x1800ead94`
- end: `0x1800eaf95`
- name: `TBGetKeyStorageLocation`
- size: `513`
- prototype: `__int64 __fastcall(int, int, int, unsigned __int16 **)`
- caller_count: `1`
- callee_count: `8`
- tags: `service_task, broker_com_uri`

## callers

- `0x1800eaf9c`

## callees

- `0x18003e890`
- `0x180047bd8`
- `0x1800ea57c`
- `0x1800ea960`
- `0x1800eac04`
- `0x1800ead94`
- `0x1800eb2b4`
- `0x1800eb368`

## import_xrefs

- `api-ms-win-core-processenvironment-l1-1-0!GetEnvironmentVariableW` at `0x1800eadd6`
- `api-ms-win-core-processenvironment-l1-1-0!GetEnvironmentVariableW` at `0x1800eae10`
- `api-ms-win-core-processenvironment-l1-1-0!GetEnvironmentVariableW` at `0x1800eadd6`
- `api-ms-win-core-processenvironment-l1-1-0!GetEnvironmentVariableW` at `0x1800eae10`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800eae1f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800eaf17`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800eae1f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800eaf17`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800eade7`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800eade7`
- `api-ms-win-shell-shellfolders-l1-1-0!SHGetKnownFolderPath` at `0x1800eae48`
- `api-ms-win-shell-shellfolders-l1-1-0!SHGetKnownFolderPath` at `0x1800eae48`

## string_xrefs

- `0x1800eadcd`: `RACSharePath`
- `0x1800eae06`: `RACSharePath`
- `0x1800eaecf`: `\Microsoft\Crypto\TokenBindingKeys\`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall TBGetKeyStorageLocation(int a1, int a2, int a3, unsigned __int16 **a4)
{
  unsigned __int16 *v8; // rdi
  DWORD EnvironmentVariableW; // eax
  DWORD v10; // ebx
  int v11; // ebx
  const GUID *v12; // rcx
  HRESULT v13; // eax
  __int64 v14; // rdx
  __int64 v15; // rax
  unsigned __int64 v16; // rsi
  unsigned __int16 *v17; // rax
  const WCHAR *v18; // rdx
  LPWSTR lpBuffer; // [rsp+40h] [rbp-58h] BYREF

  lpBuffer = 0;
  v8 = 0;
  if ( a1 )
  {
    if ( a2 )
    {
      EnvironmentVariableW = GetEnvironmentVariableW(L"RACSharePath", 0, 0);
      v10 = EnvironmentVariableW;
      if ( EnvironmentVariableW )
      {
        lpBuffer = (LPWSTR)CoTaskMemAlloc(2LL * EnvironmentVariableW);
        if ( !lpBuffer )
        {
          v11 = -2146893810;
          goto LABEL_23;
        }
        if ( GetEnvironmentVariableW(L"RACSharePath", lpBuffer, v10) )
          goto LABEL_14;
        CoTaskMemFree(lpBuffer);
        lpBuffer = 0;
      }
    }
  }
  v12 = &FOLDERID_LocalAppData;
  if ( !a1 )
    v12 = &FOLDERID_LocalAppDataLow;
  v13 = SHGetKnownFolderPath(v12, 0, 0, &lpBuffer);
  v11 = v13;
  if ( v13 < 0 )
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
      WPP_SF_dd(*((_QWORD *)WPP_GLOBAL_Control + 2), v14, WPP_GLOBAL_Control, a1 != 0, v13);
    goto LABEL_23;
  }
LABEL_14:
  v15 = -1;
  do
    ++v15;
  while ( lpBuffer[v15] );
  v16 = v15 + 72;
  v17 = (unsigned __int16 *)TBAlloc(2 * (v15 + 72));
  v8 = v17;
  if ( v17 )
  {
    v11 = StringCchCopyW(v17, v16, lpBuffer);
    if ( v11 >= 0 )
    {
      v11 = StringCchCatW(v8, v16, L"\\Microsoft\\Crypto\\TokenBindingKeys\\");
      if ( v11 >= 0 )
      {
        if ( !a3 || (v11 = TBCreateKeyDirectories(lpBuffer, v8), v11 >= 0) )
        {
          *a4 = v8;
          v8 = 0;
        }
      }
    }
  }
  else
  {
    v11 = -2146893810;
  }
LABEL_23:
  if ( lpBuffer )
    CoTaskMemFree(lpBuffer);
  if ( v8 )
    TBFree(v8);
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
  {
    v18 = L"NULL";
    if ( *a4 )
      v18 = *a4;
    WPP_SF_dddSd(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      (_DWORD)v18,
      (_DWORD)WPP_GLOBAL_Control,
      a3 != 0,
      a2 != 0,
      a1 != 0,
      (__int64)v18,
      v11);
  }
  return (unsigned int)v11;
}

```

## disassembly

```asm
0x1800ead94  push    rbx
0x1800ead96  push    rbp
0x1800ead97  push    rsi
0x1800ead98  push    rdi
0x1800ead99  push    r12
0x1800ead9b  push    r13
0x1800ead9d  push    r14
0x1800ead9f  push    r15
0x1800eada1  sub     rsp, 58h
0x1800eada5  xor     r13d, r13d
0x1800eada8  lea     rsi, WPP_GLOBAL_Control
0x1800eadaf  mov     [rsp+98h+lpBuffer], r13
0x1800eadb4  mov     r12, r9
0x1800eadb7  mov     r15d, r8d
0x1800eadba  mov     r14d, edx
0x1800eadbd  mov     ebp, ecx
0x1800eadbf  mov     edi, r13d
0x1800eadc2  test    ecx, ecx
0x1800eadc4  jz      short loc_1800EAE2A
0x1800eadc6  test    edx, edx
0x1800eadc8  jz      short loc_1800EAE2A
0x1800eadca  xor     r8d, r8d; nSize
0x1800eadcd  lea     rcx, Name; "RACSharePath"
0x1800eadd4  xor     edx, edx; lpBuffer
0x1800eadd6  call    cs:__imp_GetEnvironmentVariableW
0x1800eaddc  mov     ebx, eax
0x1800eadde  test    eax, eax
0x1800eade0  jz      short loc_1800EAE2A
0x1800eade2  mov     ecx, ebx
0x1800eade4  add     rcx, rcx; cb
0x1800eade7  call    cs:__imp_CoTaskMemAlloc
0x1800eaded  mov     [rsp+98h+lpBuffer], rax
0x1800eadf2  test    rax, rax
0x1800eadf5  jnz     short loc_1800EAE01
0x1800eadf7  mov     ebx, 8009000Eh
0x1800eadfc  jmp     loc_1800EAF0D
0x1800eae01  mov     rdx, [rsp+98h+lpBuffer]; lpBuffer
0x1800eae06  lea     rcx, Name; "RACSharePath"
0x1800eae0d  mov     r8d, ebx; nSize
0x1800eae10  call    cs:__imp_GetEnvironmentVariableW
0x1800eae16  test    eax, eax
0x1800eae18  jnz     short loc_1800EAE8A
0x1800eae1a  mov     rcx, [rsp+98h+lpBuffer]; pv
0x1800eae1f  call    cs:__imp_CoTaskMemFree
0x1800eae25  mov     [rsp+98h+lpBuffer], r13
0x1800eae2a  lea     rax, FOLDERID_LocalAppDataLow
0x1800eae31  test    ebp, ebp
0x1800eae33  lea     rcx, FOLDERID_LocalAppData
0x1800eae3a  cmovz   rcx, rax; rfid
0x1800eae3e  lea     r9, [rsp+98h+lpBuffer]; ppszPath
0x1800eae43  xor     r8d, r8d; hToken
0x1800eae46  xor     edx, edx; dwFlags
0x1800eae48  call    cs:__imp_SHGetKnownFolderPath
0x1800eae4e  mov     ebx, eax
0x1800eae50  test    eax, eax
0x1800eae52  jns     short loc_1800EAE8A
0x1800eae54  mov     r8, cs:WPP_GLOBAL_Control
0x1800eae5b  cmp     r8, rsi
0x1800eae5e  jz      loc_1800EAF0D
0x1800eae64  test    byte ptr [r8+1Ch], 4
0x1800eae69  jz      loc_1800EAF0D
0x1800eae6f  mov     rcx, [r8+10h]
0x1800eae73  test    ebp, ebp
0x1800eae75  mov     r9d, r13d
0x1800eae78  mov     [rsp+98h+var_78], eax
0x1800eae7c  setnz   r9b
0x1800eae80  call    WPP_SF_dd
0x1800eae85  jmp     loc_1800EAF0D
0x1800eae8a  mov     rcx, [rsp+98h+lpBuffer]
0x1800eae8f  or      rax, 0FFFFFFFFFFFFFFFFh
0x1800eae93  inc     rax
0x1800eae96  cmp     [rcx+rax*2], r13w
0x1800eae9b  jnz     short loc_1800EAE93
0x1800eae9d  lea     rsi, [rax+48h]
0x1800eaea1  lea     rcx, [rsi+rsi]
0x1800eaea5  call    TBAlloc
0x1800eaeaa  mov     rdi, rax
0x1800eaead  test    rax, rax
0x1800eaeb0  jnz     short loc_1800EAEB9
0x1800eaeb2  mov     ebx, 8009000Eh
0x1800eaeb7  jmp     short loc_1800EAF06
0x1800eaeb9  mov     r8, [rsp+98h+lpBuffer]; unsigned __int16 *
0x1800eaebe  mov     rdx, rsi; unsigned __int64
0x1800eaec1  mov     rcx, rdi; unsigned __int16 *
0x1800eaec4  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x1800eaec9  mov     ebx, eax
0x1800eaecb  test    eax, eax
0x1800eaecd  js      short loc_1800EAF06
0x1800eaecf  lea     r8, aMicrosoftCrypt; "\\Microsoft\\Crypto\\TokenBindingKeys\\"
0x1800eaed6  mov     rdx, rsi; unsigned __int64
0x1800eaed9  mov     rcx, rdi; unsigned __int16 *
0x1800eaedc  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x1800eaee1  mov     ebx, eax
0x1800eaee3  test    eax, eax
0x1800eaee5  js      short loc_1800EAF06
0x1800eaee7  test    r15d, r15d
0x1800eaeea  jz      short loc_1800EAEFF
0x1800eaeec  mov     rcx, [rsp+98h+lpBuffer]; unsigned __int16 *
0x1800eaef1  mov     rdx, rdi; unsigned __int16 *
0x1800eaef4  call    ?TBCreateKeyDirectories@@YAJPEBG0@Z; TBCreateKeyDirectories(ushort const *,ushort const *)
0x1800eaef9  mov     ebx, eax
0x1800eaefb  test    eax, eax
0x1800eaefd  js      short loc_1800EAF06
0x1800eaeff  mov     [r12], rdi
0x1800eaf03  mov     rdi, r13
0x1800eaf06  lea     rsi, WPP_GLOBAL_Control
0x1800eaf0d  mov     rcx, [rsp+98h+lpBuffer]; pv
0x1800eaf12  test    rcx, rcx
0x1800eaf15  jz      short loc_1800EAF1D
0x1800eaf17  call    cs:__imp_CoTaskMemFree
0x1800eaf1d  test    rdi, rdi
0x1800eaf20  jz      short loc_1800EAF2A
0x1800eaf22  mov     rcx, rdi
0x1800eaf25  call    TBFree
0x1800eaf2a  mov     r8, cs:WPP_GLOBAL_Control
0x1800eaf31  cmp     r8, rsi
0x1800eaf34  jz      short loc_1800EAF82
0x1800eaf36  test    byte ptr [r8+1Ch], 4
0x1800eaf3b  jz      short loc_1800EAF82
0x1800eaf3d  cmp     [r12], r13
0x1800eaf41  lea     rdx, aNull_1; "NULL"
0x1800eaf48  mov     ecx, r13d
0x1800eaf4b  mov     [rsp+98h+var_60], ebx
0x1800eaf4f  cmovnz  rdx, [r12]
0x1800eaf54  mov     eax, r13d
0x1800eaf57  test    ebp, ebp
0x1800eaf59  mov     [rsp+98h+var_68], rdx
0x1800eaf5e  mov     r9d, r13d
0x1800eaf61  setnz   cl
0x1800eaf64  test    r14d, r14d
0x1800eaf67  mov     [rsp+98h+var_70], ecx
0x1800eaf6b  mov     rcx, [r8+10h]
0x1800eaf6f  setnz   al
0x1800eaf72  test    r15d, r15d
0x1800eaf75  mov     [rsp+98h+var_78], eax
0x1800eaf79  setnz   r9b
0x1800eaf7d  call    WPP_SF_dddSd
0x1800eaf82  mov     eax, ebx
0x1800eaf84  add     rsp, 58h
0x1800eaf88  pop     r15
0x1800eaf8a  pop     r14
0x1800eaf8c  pop     r13
0x1800eaf8e  pop     r12
0x1800eaf90  pop     rdi
0x1800eaf91  pop     rsi
0x1800eaf92  pop     rbp
0x1800eaf93  pop     rbx
0x1800eaf94  retn
```
