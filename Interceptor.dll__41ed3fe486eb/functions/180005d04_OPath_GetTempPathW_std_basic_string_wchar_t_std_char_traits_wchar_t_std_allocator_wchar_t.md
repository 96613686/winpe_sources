# OPath::GetTempPathW(std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>> &)

- ea: `0x180005d04`
- end: `0x180005e15`
- name: `?GetTempPathW@OPath@@SAXAEAV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z`
- size: `273`
- prototype: `__int64 __fastcall(void *Src)`
- caller_count: `2`
- callee_count: `6`
- tags: `registry_config`

## callers

- `0x1800054f0`
- `0x180021610`

## callees

- `0x1800022f8`
- `0x180003f4c`
- `0x180005c70`
- `0x180005d04`
- `0x1800266e0`
- `0x1800282a0`

## import_xrefs

- `KERNEL32!GetLastError` at `0x180005de3`
- `KERNEL32!GetLastError` at `0x180005de3`
- `KERNEL32!GetTempPathW` at `0x180005d82`
- `KERNEL32!GetTempPathW` at `0x180005d82`

## string_xrefs

- `0x180005dec`: `Cannot get temp path`

## pseudocode

```c
unsigned __int64 __fastcall OPath::GetTempPathW(char *Src)
{
  DWORD *v1; // rdi
  WCHAR *v2; // rbx
  char *v3; // rax
  WCHAR *v4; // rdx
  DWORD TempPathW; // eax
  unsigned __int64 v6; // rdx
  unsigned __int64 result; // rax
  DWORD LastError; // eax
  __int64 v9; // rdx
  _BYTE pExceptionObject[912]; // [rsp+20h] [rbp-3A8h] BYREF

  v1 = (DWORD *)(Src + 24);
  v2 = (WCHAR *)Src;
  if ( *((_QWORD *)Src + 2) < 0x104u )
  {
    _mm_lfence();
    std::wstring::append(Src);
  }
  else
  {
    *((_QWORD *)Src + 2) = 260;
    v3 = Src;
    if ( *(_QWORD *)v1 > 7u )
      v3 = *(char **)Src;
    *((_WORD *)v3 + 260) = 0;
  }
  v4 = v2;
  if ( *(_QWORD *)v1 > 7u )
    v4 = *(WCHAR **)v2;
  if ( *(_QWORD *)v1 > 0xFFFFFFFF )
    OcfxSafeIntExceptionPolicy::SafeIntOnOverflow();
  TempPathW = GetTempPathW(*v1, v4);
  v6 = TempPathW;
  if ( !TempPathW )
  {
    LastError = GetLastError();
    OException::OException(pExceptionObject, v9, LastError, L"Cannot get temp path");
    throw (OException *)pExceptionObject;
  }
  result = *((_QWORD *)v2 + 2);
  if ( v6 > result )
  {
    _mm_lfence();
    return std::wstring::append(v2);
  }
  else
  {
    *((_QWORD *)v2 + 2) = v6;
    if ( *(_QWORD *)v1 > 7u )
    {
      _mm_lfence();
      v2 = *(WCHAR **)v2;
    }
    v2[v6] = 0;
  }
  return result;
}

```

## disassembly

```asm
0x180005d04  mov     [rsp+arg_8], rbx
0x180005d09  mov     [rsp+arg_10], rsi
0x180005d0e  push    rdi
0x180005d0f  sub     rsp, 3C0h
0x180005d16  mov     rax, cs:__security_cookie
0x180005d1d  xor     rax, rsp
0x180005d20  mov     [rsp+3C8h+var_18], rax
0x180005d28  mov     rax, [rcx+10h]
0x180005d2c  lea     rdi, [rcx+18h]
0x180005d30  xor     esi, esi
0x180005d32  mov     edx, 104h
0x180005d37  mov     rbx, rcx
0x180005d3a  cmp     rax, rdx
0x180005d3d  jb      short loc_180005D58
0x180005d3f  mov     [rcx+10h], rdx
0x180005d43  mov     rax, rcx
0x180005d46  cmp     qword ptr [rdi], 7
0x180005d4a  jbe     short loc_180005D4F
0x180005d4c  mov     rax, [rcx]
0x180005d4f  mov     [rax+208h], si
0x180005d56  jmp     short loc_180005D66
0x180005d58  lfence
0x180005d5b  xor     r8d, r8d
0x180005d5e  sub     rdx, rax
0x180005d61  call    ?append@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAAAEAV12@_K_W@Z; std::wstring::append(unsigned __int64,wchar_t)
0x180005d66  cmp     qword ptr [rdi], 7
0x180005d6a  mov     rdx, rbx
0x180005d6d  jbe     short loc_180005D72
0x180005d6f  mov     rdx, [rbx]; lpBuffer
0x180005d72  mov     eax, 0FFFFFFFFh
0x180005d77  cmp     [rdi], rax
0x180005d7a  ja      loc_180005E0F
0x180005d80  mov     ecx, [rdi]; nBufferLength
0x180005d82  call    cs:__imp_GetTempPathW
0x180005d88  mov     edx, eax
0x180005d8a  test    eax, eax
0x180005d8c  jz      short loc_180005DE3
0x180005d8e  mov     rax, [rbx+10h]
0x180005d92  cmp     rdx, rax
0x180005d95  ja      short loc_180005DAD
0x180005d97  mov     [rbx+10h], rdx
0x180005d9b  cmp     qword ptr [rdi], 7
0x180005d9f  jbe     short loc_180005DA7
0x180005da1  lfence
0x180005da4  mov     rbx, [rbx]
0x180005da7  mov     [rbx+rdx*2], si
0x180005dab  jmp     short loc_180005DBE
0x180005dad  lfence
0x180005db0  xor     r8d, r8d
0x180005db3  sub     rdx, rax
0x180005db6  mov     rcx, rbx; Src
0x180005db9  call    ?append@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAAAEAV12@_K_W@Z; std::wstring::append(unsigned __int64,wchar_t)
0x180005dbe  mov     rcx, [rsp+3C8h+var_18]
0x180005dc6  xor     rcx, rsp; StackCookie
0x180005dc9  call    __security_check_cookie
0x180005dce  lea     r11, [rsp+3C8h+var_8]
0x180005dd6  mov     rbx, [r11+18h]
0x180005dda  mov     rsi, [r11+20h]
0x180005dde  mov     rsp, r11
0x180005de1  pop     rdi
0x180005de2  retn
0x180005de3  call    cs:__imp_GetLastError
0x180005de9  mov     r8d, eax
0x180005dec  lea     r9, aCannotGetTempP; "Cannot get temp path"
0x180005df3  lea     rcx, [rsp+3C8h+pExceptionObject]
0x180005df8  call    ??$?0$0BF@@OException@@QEAA@W4exceptionType@et@@IAEAY0BF@$$CB_W@Z; OException::OException(et::exceptionType,uint,wchar_t const (&)[21])
0x180005dfd  lea     rdx, _TI2?AVOException@@; pThrowInfo
0x180005e04  lea     rcx, [rsp+3C8h+pExceptionObject]; pExceptionObject
0x180005e09  call    _CxxThrowException
0x180005e0f  call    ?SafeIntOnOverflow@OcfxSafeIntExceptionPolicy@@SAXXZ; OcfxSafeIntExceptionPolicy::SafeIntOnOverflow(void)
```
