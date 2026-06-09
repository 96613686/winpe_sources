# CTemplate::GetLanguageEquivalents(void)

- ea: `0x180016c3c`
- end: `0x180016cea`
- name: `?GetLanguageEquivalents@CTemplate@@AEAAXXZ`
- size: `174`
- prototype: `void __fastcall(CTemplate *__hidden this)`
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, service_task`

## callers

- `0x1800140a0`

## callees

- `0x180016250`
- `0x180016c3c`
- `0x180016cf0`
- `0x180023d86`
- `0x180023dd0`
- `0x18005fadc`

## import_xrefs

- `msvcrt!strncpy_s` at `0x18002d837`
- `msvcrt!strncpy_s` at `0x18002d837`
- `msvcrt!strcpy_s` at `0x18002d821`
- `msvcrt!strcpy_s` at `0x18002d821`
- `ADVAPI32!RegCloseKey` at `0x18002d905`
- `ADVAPI32!RegCloseKey` at `0x18002d92f`
- `ADVAPI32!RegCloseKey` at `0x18002d905`
- `ADVAPI32!RegCloseKey` at `0x18002d92f`
- `ADVAPI32!RegOpenKeyExA` at `0x18002d869`
- `ADVAPI32!RegOpenKeyExA` at `0x18002d869`
- `KERNEL32!SetLastError` at `0x18002d7fc`
- `KERNEL32!SetLastError` at `0x18002d7fc`
- `KERNEL32!RaiseException` at `0x18002d91e`
- `KERNEL32!RaiseException` at `0x18002d91e`
- `iisutil!?Resize@BUFFER@@QEAA_NK@Z` at `0x18002d7ed`
- `iisutil!?Resize@BUFFER@@QEAA_NK@Z` at `0x18002d7ed`
- `iisutil!?QueryPtr@BUFFER@@QEBAPEAXXZ` at `0x18002d80c`
- `iisutil!?QueryPtr@BUFFER@@QEBAPEAXXZ` at `0x18002d80c`
- `iisutil!??0BUFFER@@QEAA@PEAEK@Z` at `0x18002d7dc`
- `iisutil!??0BUFFER@@QEAA@PEAEK@Z` at `0x18002d7dc`
- `iisutil!??1BUFFER@@QEAA@XZ` at `0x18002d93a`
- `iisutil!??1BUFFER@@QEAA@XZ` at `0x18002d93a`

## string_xrefs

- `0x18002d817`: `SYSTEM\CurrentControlSet\Services\W3SVC\ASP\LanguageEngines\`
- `0x18002d8a6`: `Write`
- `0x18002d8e6`: `WriteBlock`

## pseudocode

```c
void __fastcall CTemplate::GetLanguageEquivalents(CTemplate *this)
{
  rsize_t v2; // r15
  char *Ptr; // rsi
  HKEY hKey; // [rsp+40h] [rbp-278h] BYREF
  char *Source; // [rsp+48h] [rbp-270h] BYREF
  rsize_t MaxCount; // [rsp+50h] [rbp-268h]
  __int64 v7; // [rsp+58h] [rbp-260h]
  _BYTE v8[48]; // [rsp+60h] [rbp-258h] BYREF
  unsigned __int8 v9[512]; // [rsp+90h] [rbp-228h] BYREF

  Source = 0;
  MaxCount = 0;
  v7 = 0;
  CTemplate::CBuffer::GetItem((CTemplate::CBuffer *)(*((_QWORD *)this + 6) + 88LL), 0, (struct CByteRange *)&Source);
  if ( Source )
  {
    v2 = (unsigned int)MaxCount;
    if ( (_DWORD)MaxCount )
    {
      if ( !CByteRange::FMatchesSz((CByteRange *)&Source, "VBScript")
        && !CByteRange::FMatchesSz((CByteRange *)&Source, "JScript")
        && !CByteRange::FMatchesSz((CByteRange *)&Source, "JavaScript")
        && !CByteRange::FMatchesSz((CByteRange *)&Source, "LiveScript") )
      {
        memset_0(v9, 0, sizeof(v9));
        BUFFER::BUFFER((BUFFER *)v8, v9, 0x200u);
        if ( BUFFER::Resize((BUFFER *)v8, v2 + 61) )
        {
          Ptr = (char *)BUFFER::QueryPtr((BUFFER *)v8);
          strcpy_s(Ptr, (unsigned int)(v2 + 61), "SYSTEM\\CurrentControlSet\\Services\\W3SVC\\ASP\\LanguageEngines\\");
          strncpy_s(Ptr + 60, (unsigned int)(v2 + 1), Source, v2);
          Ptr[v2 + 60] = 0;
          hKey = 0;
          if ( !RegOpenKeyExA(HKEY_LOCAL_MACHINE, Ptr, 0, 1u, &hKey) )
          {
            CTemplate::SetLanguageEquivalent(
              (CTemplate *)(*((_QWORD *)this + 6) + 192LL),
              hKey,
              "Write",
              (char **)(*((_QWORD *)this + 6) + 184LL),
              (unsigned int *)(*((_QWORD *)this + 6) + 232LL),
              (char **)(*((_QWORD *)this + 6) + 192LL),
              (unsigned int *)(*((_QWORD *)this + 6) + 236LL));
            CTemplate::SetLanguageEquivalent(
              (CTemplate *)(*((_QWORD *)this + 6) + 176LL),
              hKey,
              "WriteBlock",
              (char **)(*((_QWORD *)this + 6) + 168LL),
              (unsigned int *)(*((_QWORD *)this + 6) + 224LL),
              (char **)(*((_QWORD *)this + 6) + 176LL),
              (unsigned int *)(*((_QWORD *)this + 6) + 228LL));
          }
          if ( hKey )
            RegCloseKey(hKey);
        }
        else
        {
          SetLastError(0x8007000E);
        }
        BUFFER::~BUFFER((BUFFER *)v8);
      }
    }
  }
}

```

## disassembly

```asm
0x180016c3c  mov     [rsp+arg_8], rbx
0x180016c41  mov     [rsp+arg_10], rsi
0x180016c46  push    rdi
0x180016c47  push    r13
0x180016c49  push    r15
0x180016c4b  sub     rsp, 2A0h
0x180016c52  mov     rax, cs:__security_cookie
0x180016c59  xor     rax, rsp
0x180016c5c  mov     [rsp+2B8h+var_28], rax
0x180016c64  mov     r13, rcx
0x180016c67  mov     [rsp+2B8h+Source], 0
0x180016c70  mov     [rsp+2B8h+MaxCount], 0
0x180016c79  mov     [rsp+2B8h+var_260], 0
0x180016c82  mov     rcx, [rcx+30h]
0x180016c86  add     rcx, 58h ; 'X'; this
0x180016c8a  lea     r8, [rsp+2B8h+Source]; struct CByteRange *
0x180016c8f  xor     edx, edx; unsigned int
0x180016c91  call    ?GetItem@CBuffer@CTemplate@@QEAAXIAEAVCByteRange@@@Z; CTemplate::CBuffer::GetItem(uint,CByteRange &)
0x180016c96  cmp     [rsp+2B8h+Source], 0
0x180016c9c  jz      short loc_180016CC1
0x180016c9e  mov     r15d, dword ptr [rsp+2B8h+MaxCount]
0x180016ca3  test    r15d, r15d
0x180016ca6  jz      short loc_180016CC1
0x180016ca8  lea     rdx, aVbscript; "VBScript"
0x180016caf  lea     rcx, [rsp+2B8h+Source]; this
0x180016cb4  call    ?FMatchesSz@CByteRange@@QEAAEPEBD@Z; CByteRange::FMatchesSz(char const *)
0x180016cb9  test    al, al
0x180016cbb  jz      loc_18002D76A
0x180016cc1  mov     rcx, [rsp+2B8h+var_28]
0x180016cc9  xor     rcx, rsp; StackCookie
0x180016ccc  call    __security_check_cookie
0x180016cd1  lea     r11, [rsp+2B8h+var_18]
0x180016cd9  mov     rbx, [r11+28h]
0x180016cdd  mov     rsi, [r11+30h]
0x180016ce1  mov     rsp, r11
0x180016ce4  pop     r15
0x180016ce6  pop     r13
0x180016ce8  pop     rdi
0x180016ce9  retn
0x18002d76a  lea     rdx, aJscript; "JScript"
0x18002d771  lea     rcx, [rsp+2B8h+Source]; this
0x18002d776  call    ?FMatchesSz@CByteRange@@QEAAEPEBD@Z; CByteRange::FMatchesSz(char const *)
0x18002d77b  test    al, al
0x18002d77d  jnz     loc_180016CC1
0x18002d783  lea     rdx, aJavascript; "JavaScript"
0x18002d78a  lea     rcx, [rsp+2B8h+Source]; this
0x18002d78f  call    ?FMatchesSz@CByteRange@@QEAAEPEBD@Z; CByteRange::FMatchesSz(char const *)
0x18002d794  test    al, al
0x18002d796  jnz     loc_180016CC1
0x18002d79c  lea     rdx, aLivescript; "LiveScript"
0x18002d7a3  lea     rcx, [rsp+2B8h+Source]; this
0x18002d7a8  call    ?FMatchesSz@CByteRange@@QEAAEPEBD@Z; CByteRange::FMatchesSz(char const *)
0x18002d7ad  test    al, al
0x18002d7af  jnz     loc_180016CC1
0x18002d7b5  mov     ebx, 200h
0x18002d7ba  mov     r8d, ebx; Size
0x18002d7bd  xor     edx, edx; Val
0x18002d7bf  lea     rcx, [rsp+2B8h+var_228]; void *
0x18002d7c7  call    memset_0
0x18002d7cc  mov     r8d, ebx
0x18002d7cf  lea     rdx, [rsp+2B8h+var_228]
0x18002d7d7  lea     rcx, [rsp+2B8h+var_258]
0x18002d7dc  call    cs:__imp_??0BUFFER@@QEAA@PEAEK@Z; BUFFER::BUFFER(uchar *,ulong)
0x18002d7e2  lea     ebx, [r15+3Dh]
0x18002d7e6  mov     edx, ebx
0x18002d7e8  lea     rcx, [rsp+2B8h+var_258]
0x18002d7ed  call    cs:__imp_?Resize@BUFFER@@QEAA_NK@Z; BUFFER::Resize(ulong)
0x18002d7f3  test    al, al
0x18002d7f5  jnz     short loc_18002D807
0x18002d7f7  mov     ecx, 8007000Eh; dwErrCode
0x18002d7fc  call    cs:__imp_SetLastError
0x18002d802  jmp     loc_18002D935
0x18002d807  lea     rcx, [rsp+2B8h+var_258]
0x18002d80c  call    cs:__imp_?QueryPtr@BUFFER@@QEBAPEAXXZ; BUFFER::QueryPtr(void)
0x18002d812  mov     rsi, rax
0x18002d815  mov     edx, ebx; SizeInBytes
0x18002d817  lea     r8, aSystemCurrentc_1; "SYSTEM\\CurrentControlSet\\Services\\W3"...
0x18002d81e  mov     rcx, rax; Destination
0x18002d821  call    cs:__imp_strcpy_s
0x18002d827  lea     edx, [r15+1]; SizeInBytes
0x18002d82b  mov     r9, r15; MaxCount
0x18002d82e  mov     r8, [rsp+2B8h+Source]; Source
0x18002d833  lea     rcx, [rsi+3Ch]; Destination
0x18002d837  call    cs:__imp_strncpy_s
0x18002d83d  mov     byte ptr [r15+rsi+3Ch], 0
0x18002d843  mov     [rsp+2B8h+hKey], 0
0x18002d84c  lea     rax, [rsp+2B8h+hKey]
0x18002d851  mov     [rsp+2B8h+phkResult], rax; phkResult
0x18002d856  mov     r9d, 1; samDesired
0x18002d85c  xor     r8d, r8d; ulOptions
0x18002d85f  mov     rdx, rsi; lpSubKey
0x18002d862  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18002d869  call    cs:__imp_RegOpenKeyExA
0x18002d86f  test    eax, eax
0x18002d871  jnz     loc_18002D925
0x18002d877  mov     r9, [r13+30h]
0x18002d87b  lea     rax, [r9+0ECh]
0x18002d882  lea     rcx, [r9+0C0h]; this
0x18002d889  lea     rdx, [r9+0E8h]
0x18002d890  add     r9, 0B8h; char **
0x18002d897  mov     [rsp+2B8h+var_288], rax; unsigned int *
0x18002d89c  mov     [rsp+2B8h+var_290], rcx; char **
0x18002d8a1  mov     [rsp+2B8h+phkResult], rdx; unsigned int *
0x18002d8a6  lea     r8, aWrite_0; "Write"
0x18002d8ad  mov     rdx, [rsp+2B8h+hKey]; void *
0x18002d8b2  call    ?SetLanguageEquivalent@CTemplate@@AEAAXPEAXPEADPEAPEADPEAI23@Z; CTemplate::SetLanguageEquivalent(void *,char *,char * *,uint *,char * *,uint *)
0x18002d8b7  mov     r9, [r13+30h]
0x18002d8bb  lea     rax, [r9+0E4h]
0x18002d8c2  lea     rcx, [r9+0B0h]; this
0x18002d8c9  lea     rdx, [r9+0E0h]
0x18002d8d0  add     r9, 0A8h; char **
0x18002d8d7  mov     [rsp+2B8h+var_288], rax; unsigned int *
0x18002d8dc  mov     [rsp+2B8h+var_290], rcx; char **
0x18002d8e1  mov     [rsp+2B8h+phkResult], rdx; unsigned int *
0x18002d8e6  lea     r8, aWriteblock; "WriteBlock"
0x18002d8ed  mov     rdx, [rsp+2B8h+hKey]; void *
0x18002d8f2  call    ?SetLanguageEquivalent@CTemplate@@AEAAXPEAXPEADPEAPEADPEAI23@Z; CTemplate::SetLanguageEquivalent(void *,char *,char * *,uint *,char * *,uint *)
0x18002d8f7  jmp     short loc_18002D925
0x18002d8f9  mov     ebx, eax
0x18002d8fb  mov     rcx, [rsp+2B8h+hKey]; hKey
0x18002d900  test    rcx, rcx
0x18002d903  jz      short loc_18002D914
0x18002d905  call    cs:__imp_RegCloseKey
0x18002d90b  mov     [rsp+2B8h+hKey], 0
0x18002d914  xor     r9d, r9d; lpArguments
0x18002d917  xor     r8d, r8d; nNumberOfArguments
0x18002d91a  xor     edx, edx; dwExceptionFlags
0x18002d91c  mov     ecx, ebx; dwExceptionCode
0x18002d91e  call    cs:__imp_RaiseException
0x18002d924  nop
0x18002d925  mov     rcx, [rsp+2B8h+hKey]; hKey
0x18002d92a  test    rcx, rcx
0x18002d92d  jz      short loc_18002D935
0x18002d92f  call    cs:__imp_RegCloseKey
0x18002d935  lea     rcx, [rsp+2B8h+var_258]
0x18002d93a  call    cs:__imp_??1BUFFER@@QEAA@XZ; BUFFER::~BUFFER(void)
0x18002d940  nop
0x18002d941  jmp     loc_180016CC1
```
