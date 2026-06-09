# AudMigLibSetupLog(ushort const *,...)

- ea: `0x180012e80`
- end: `0x180012fc7`
- name: `?AudMigLibSetupLog@@YAXPEBGZZ`
- size: `327`
- prototype: `void(const unsigned __int16 *, ...)`
- caller_count: `12`
- callee_count: `5`
- tags: `installer_update`

## callers

- `0x180012acc`
- `0x180012fd0`
- `0x18001343c`
- `0x180025e48`
- `0x180034c84`
- `0x18003735c`
- `0x1800395ec`
- `0x180039d90`
- `0x180039ef4`
- `0x18003a6c8`
- `0x18003cb70`
- `0x18005ab60`

## callees

- `0x180012e80`
- `0x18003e920`
- `0x18003f7c8`
- `0x18003f81c`
- `0x180040940`

## import_xrefs

- `ext-ms-win-setupapi-logging-l1-1-0!SetupLogErrorW` at `0x180012f8e`
- `ext-ms-win-setupapi-logging-l1-1-0!SetupLogErrorW` at `0x180012f8e`
- `ext-ms-win-setupapi-logging-l1-1-0!SetupOpenLog` at `0x180012f7d`
- `ext-ms-win-setupapi-logging-l1-1-0!SetupOpenLog` at `0x180012f7d`
- `ext-ms-win-setupapi-logging-l1-1-0!SetupCloseLog` at `0x180012f94`
- `ext-ms-win-setupapi-logging-l1-1-0!SetupCloseLog` at `0x180012f94`

## pseudocode

```c
void AudMigLibSetupLog(const unsigned __int16 *a1, ...)
{
  unsigned __int64 v1; // rcx
  wchar_t *v2; // rax
  wchar_t *v3; // rdi
  unsigned __int64 v4; // rbx
  int v5; // eax
  wchar_t Buffer[1024]; // [rsp+30h] [rbp-828h] BYREF
  va_list Args; // [rsp+868h] [rbp+10h] BYREF

  va_start(Args, a1);
  if ( (unsigned __int8)IsSetupCloseLogPresent()
    && (unsigned __int8)IsSetupCloseLogPresent()
    && (unsigned __int8)IsSetupCloseLogPresent() )
  {
    swprintf_s(Buffer, 0x400u, L"AudMig: ");
    v1 = 1024;
    v2 = Buffer;
    do
    {
      if ( !*v2 )
        break;
      ++v2;
      --v1;
    }
    while ( v1 );
    if ( v1 )
    {
      v3 = &Buffer[1024 - v1];
      if ( v1 > 0x7FFFFFFF )
      {
        *v3 = 0;
      }
      else
      {
        v4 = v1 - 1;
        v5 = vsnwprintf(v3, v1 - 1, a1, Args);
        if ( v5 < 0 || v5 == v4 || v5 > v4 )
          v3[v4] = 0;
      }
      if ( SetupOpenLog(0) )
      {
        SetupLogErrorW(Buffer, 0);
        SetupCloseLog();
      }
    }
  }
}

```

## disassembly

```asm
0x180012e80  mov     [rsp+Format], rcx
0x180012e85  mov     qword ptr [rsp+Args], rdx
0x180012e8a  mov     [rsp+arg_10], r8
0x180012e8f  mov     [rsp+arg_18], r9
0x180012e94  sub     rsp, 858h
0x180012e9b  mov     rax, cs:__security_cookie
0x180012ea2  xor     rax, rsp
0x180012ea5  mov     [rsp+858h+var_28], rax
0x180012ead  call    IsSetupCloseLogPresent
0x180012eb2  test    al, al
0x180012eb4  jz      loc_180012FA2
0x180012eba  call    IsSetupCloseLogPresent
0x180012ebf  test    al, al
0x180012ec1  jz      loc_180012FA2
0x180012ec7  call    IsSetupCloseLogPresent
0x180012ecc  test    al, al
0x180012ece  jz      loc_180012FA2
0x180012ed4  mov     [rsp+858h+var_8], rbx
0x180012edc  lea     r8, aAudmig
0x180012ee3  mov     ebx, 400h
0x180012ee8  mov     [rsp+858h+var_838], 0
0x180012ef1  mov     edx, ebx; BufferCount
0x180012ef3  lea     rcx, [rsp+858h+Buffer]; Buffer
0x180012ef8  call    swprintf_s
0x180012efd  lea     r9, [rsp+858h+Args]; Args
0x180012f05  mov     ecx, ebx
0x180012f07  lea     rax, [rsp+858h+Buffer]
0x180012f0c  nop     dword ptr [rax+00h]
0x180012f10  cmp     word ptr [rax], 0
0x180012f14  jz      short loc_180012F20
0x180012f16  add     rax, 2
0x180012f1a  sub     rcx, 1
0x180012f1e  jnz     short loc_180012F10
0x180012f20  xor     eax, eax
0x180012f22  mov     rdx, rbx
0x180012f25  sub     rdx, rcx
0x180012f28  test    rcx, rcx
0x180012f2b  cmovz   rdx, rax
0x180012f2f  jz      short loc_180012F9A
0x180012f31  sub     rbx, rdx
0x180012f34  jz      short loc_180012F7B
0x180012f36  mov     [rsp+858h+var_10], rdi
0x180012f3e  lea     rdi, [rsp+858h+Buffer]
0x180012f43  lea     rdi, [rdi+rdx*2]
0x180012f47  cmp     rbx, 7FFFFFFFh
0x180012f4e  ja      short loc_180012FC2
0x180012f50  mov     r8, [rsp+858h+Format]; Format
0x180012f58  dec     rbx
0x180012f5b  mov     rdx, rbx; BufferCount
0x180012f5e  mov     rcx, rdi; Buffer
0x180012f61  call    _vsnwprintf
0x180012f66  test    eax, eax
0x180012f68  js      short loc_180012FBA
0x180012f6a  cdqe
0x180012f6c  cmp     rax, rbx
0x180012f6f  jz      short loc_180012FBA
0x180012f71  ja      short loc_180012FBA
0x180012f73  mov     rdi, [rsp+858h+var_10]
0x180012f7b  xor     ecx, ecx; Erase
0x180012f7d  call    cs:__imp_SetupOpenLog
0x180012f83  test    eax, eax
0x180012f85  jz      short loc_180012F9A
0x180012f87  xor     edx, edx; Severity
0x180012f89  lea     rcx, [rsp+858h+Buffer]; MessageString
0x180012f8e  call    cs:__imp_SetupLogErrorW
0x180012f94  call    cs:__imp_SetupCloseLog
0x180012f9a  mov     rbx, [rsp+858h+var_8]
0x180012fa2  mov     rcx, [rsp+858h+var_28]
0x180012faa  xor     rcx, rsp; StackCookie
0x180012fad  call    __security_check_cookie
0x180012fb2  add     rsp, 858h
0x180012fb9  retn
0x180012fba  xor     eax, eax
0x180012fbc  mov     [rdi+rbx*2], ax
0x180012fc0  jmp     short loc_180012F73
0x180012fc2  mov     [rdi], ax
0x180012fc5  jmp     short loc_180012F73
```
