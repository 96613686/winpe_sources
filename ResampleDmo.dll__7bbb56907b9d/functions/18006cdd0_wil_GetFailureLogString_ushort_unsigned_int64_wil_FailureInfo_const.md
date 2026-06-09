# wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)

- ea: `0x18006cdd0`
- end: `0x18006d083`
- name: `?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z`
- size: `691`
- prototype: `__int64 __fastcall(wil *__hidden this, unsigned __int16 *, unsigned __int64, const struct wil::FailureInfo *)`
- caller_count: `1`
- callee_count: `5`
- tags: ``

## callers

- `0x18006c4e0`

## callees

- `0x18000ab90`
- `0x18000b79c`
- `0x18006cdd0`
- `0x18006d430`
- `0x180085010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18006cf86`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18006cf86`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x18006cf05`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x18006cf05`

## pseudocode

```c
__int64 __fastcall wil::GetFailureLogString(
        wil *this,
        unsigned __int16 *a2,
        __int64 a3,
        const struct wil::FailureInfo *a4)
{
  __int64 result; // rax
  const char *v8; // rdi
  DWORD v9; // ebp
  unsigned __int16 *v10; // rsi
  const unsigned __int16 *v11; // r9
  __int64 v12; // rax
  const unsigned __int16 *v13; // rcx
  unsigned __int16 *v14; // rax
  wil::details *v15; // r14
  const unsigned __int16 *v16; // r9
  wil::details *v17; // rax
  const unsigned __int16 *v18; // r9
  unsigned __int16 *v19; // rax
  const unsigned __int16 *v20; // r9
  const unsigned __int16 *v21; // r9
  const unsigned __int16 *v22; // r9
  LPWSTR lpBuffer; // [rsp+20h] [rbp-258h]
  LPWSTR lpBuffera; // [rsp+20h] [rbp-258h]
  DWORD nSize[2]; // [rsp+28h] [rbp-250h]
  va_list *Arguments; // [rsp+30h] [rbp-248h]
  WCHAR Buffer[256]; // [rsp+40h] [rbp-238h] BYREF

  result = 0;
  if ( a2 && this )
  {
    *(_WORD *)this = 0;
    if ( !g_pfnResultLoggingCallback
      || !wil::details::g_resultMessageCallbackSet
      || (g_pfnResultLoggingCallback(a3, this, a2), !*(_WORD *)this) )
    {
      if ( *(_DWORD *)a3 )
      {
        switch ( *(_DWORD *)a3 )
        {
          case 1:
            v8 = "ReturnNt";
            if ( (*(_BYTE *)(a3 + 4) & 8) == 0 )
              v8 = "ReturnHr";
            break;
          case 2:
            v8 = "LogNt";
            if ( (*(_BYTE *)(a3 + 4) & 8) == 0 )
              v8 = "LogHr";
            break;
          case 3:
            v8 = "FailFast";
            break;
          default:
            v8 = (const char *)&byte_180088A5F;
            break;
        }
      }
      else
      {
        v8 = "Exception";
      }
      memset_0(Buffer, 0, sizeof(Buffer));
      if ( (*(_BYTE *)(a3 + 4) & 8) != 0 )
      {
        v9 = *(_DWORD *)(a3 + 12);
        if ( wil::details::g_pfnFormatNtStatusMsg )
          wil::details::g_pfnFormatNtStatusMsg(v9, Buffer, 0x100u);
      }
      else
      {
        v9 = *(_DWORD *)(a3 + 8);
        FormatMessageW(0x1200u, 0, v9, 0x400u, Buffer, 0x100u, 0);
      }
      v10 = (unsigned __int16 *)((char *)this + 2 * (_QWORD)a2);
      v11 = *(const unsigned __int16 **)(a3 + 56);
      v12 = *(_QWORD *)(a3 + 136);
      v13 = *(const unsigned __int16 **)(a3 + 128);
      if ( v11 )
      {
        LODWORD(lpBuffer) = *(_DWORD *)(a3 + 64);
        v14 = wil::details::LogStringPrintf(this, v10, L"%hs(%u)\\%hs!%p: ", v11, lpBuffer, v13, v12);
      }
      else
      {
        v14 = wil::details::LogStringPrintf(this, v10, L"%hs!%p: ", v13, v12);
      }
      v15 = (wil::details *)v14;
      v16 = *(const unsigned __int16 **)(a3 + 144);
      if ( v16 )
        v15 = (wil::details *)wil::details::LogStringPrintf((wil::details *)v14, v10, L"(caller: %p) ", v16);
      LODWORD(Arguments) = v9;
      nSize[0] = GetCurrentThreadId();
      LODWORD(lpBuffera) = *(_DWORD *)(a3 + 68);
      v17 = (wil::details *)wil::details::LogStringPrintf(
                              v15,
                              v10,
                              L"%hs(%d) tid(%x) %08X %ws",
                              (const unsigned __int16 *)v8,
                              lpBuffera,
                              *(_QWORD *)nSize,
                              Arguments,
                              Buffer);
      if ( *(_QWORD *)(a3 + 24) || *(_QWORD *)(a3 + 72) || *(_QWORD *)(a3 + 48) )
      {
        v19 = wil::details::LogStringPrintf(v17, v10, L"    ", v18);
        v20 = *(const unsigned __int16 **)(a3 + 24);
        if ( v20 )
          v19 = wil::details::LogStringPrintf((wil::details *)v19, v10, L"Msg:[%ws] ", v20);
        v21 = *(const unsigned __int16 **)(a3 + 72);
        if ( v21 )
          v19 = wil::details::LogStringPrintf((wil::details *)v19, v10, L"CallContext:[%hs] ", v21);
        v22 = *(const unsigned __int16 **)(a3 + 48);
        if ( *(_QWORD *)(a3 + 40) )
        {
          wil::details::LogStringPrintf((wil::details *)v19, v10, L"[%hs(%hs)]\n", v22, *(_QWORD *)(a3 + 40));
        }
        else if ( v22 )
        {
          wil::details::LogStringPrintf((wil::details *)v19, v10, L"[%hs]\n", v22);
        }
        else
        {
          wil::details::LogStringPrintf((wil::details *)v19, v10, L"\n", 0);
        }
      }
    }
    return 0;
  }
  return result;
}

```

## disassembly

```asm
0x18006cdd0  push    rbx
0x18006cdd2  push    rbp
0x18006cdd3  push    rsi
0x18006cdd4  push    rdi
0x18006cdd5  push    r14
0x18006cdd7  sub     rsp, 250h
0x18006cdde  mov     rax, cs:__security_cookie
0x18006cde5  xor     rax, rsp
0x18006cde8  mov     [rsp+278h+var_38], rax
0x18006cdf0  mov     rbx, r8
0x18006cdf3  mov     rsi, rdx
0x18006cdf6  mov     r14, rcx
0x18006cdf9  xor     eax, eax
0x18006cdfb  test    rdx, rdx
0x18006cdfe  jz      loc_18006D065
0x18006ce04  test    rcx, rcx
0x18006ce07  jz      loc_18006D065
0x18006ce0d  mov     [rcx], ax
0x18006ce10  mov     rax, cs:g_pfnResultLoggingCallback
0x18006ce17  test    rax, rax
0x18006ce1a  jz      short loc_18006CE3E
0x18006ce1c  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, 0; bool wil::details::g_resultMessageCallbackSet
0x18006ce23  jz      short loc_18006CE3E
0x18006ce25  mov     r8, rdx
0x18006ce28  mov     rdx, rcx
0x18006ce2b  mov     rcx, rbx
0x18006ce2e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006ce33  cmp     word ptr [r14], 0
0x18006ce38  jnz     loc_18006D063
0x18006ce3e  mov     ecx, [rbx]
0x18006ce40  test    ecx, ecx
0x18006ce42  jz      short loc_18006CE95
0x18006ce44  sub     ecx, 1
0x18006ce47  jz      short loc_18006CE7D
0x18006ce49  sub     ecx, 1
0x18006ce4c  jz      short loc_18006CE65
0x18006ce4e  cmp     ecx, 1
0x18006ce51  jz      short loc_18006CE5C
0x18006ce53  lea     rdi, byte_180088A5F
0x18006ce5a  jmp     short loc_18006CE9C
0x18006ce5c  lea     rdi, aFailfast; "FailFast"
0x18006ce63  jmp     short loc_18006CE9C
0x18006ce65  test    byte ptr [rbx+4], 8
0x18006ce69  lea     rax, aLoghr; "LogHr"
0x18006ce70  lea     rdi, aLognt; "LogNt"
0x18006ce77  cmovz   rdi, rax
0x18006ce7b  jmp     short loc_18006CE9C
0x18006ce7d  test    byte ptr [rbx+4], 8
0x18006ce81  lea     rax, aReturnhr; "ReturnHr"
0x18006ce88  lea     rdi, aReturnnt; "ReturnNt"
0x18006ce8f  cmovz   rdi, rax
0x18006ce93  jmp     short loc_18006CE9C
0x18006ce95  lea     rdi, aException; "Exception"
0x18006ce9c  xor     edx, edx; Val
0x18006ce9e  mov     r8d, 200h; Size
0x18006cea4  lea     rcx, [rsp+278h+Buffer]; void *
0x18006cea9  call    memset_0
0x18006ceae  test    byte ptr [rbx+4], 8
0x18006ceb2  jz      short loc_18006CED7
0x18006ceb4  mov     ebp, [rbx+0Ch]
0x18006ceb7  mov     rax, cs:?g_pfnFormatNtStatusMsg@details@wil@@3P6AXJPEAGK@ZEA; void (*wil::details::g_pfnFormatNtStatusMsg)(long,ushort *,ulong)
0x18006cebe  test    rax, rax
0x18006cec1  jz      short loc_18006CF0B
0x18006cec3  mov     r8d, 100h
0x18006cec9  lea     rdx, [rsp+278h+Buffer]
0x18006cece  mov     ecx, ebp
0x18006ced0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006ced5  jmp     short loc_18006CF0B
0x18006ced7  mov     ebp, [rbx+8]
0x18006ceda  mov     [rsp+278h+Arguments], 0; Arguments
0x18006cee3  mov     [rsp+278h+nSize], 100h; nSize
0x18006ceeb  lea     rax, [rsp+278h+Buffer]
0x18006cef0  mov     [rsp+278h+lpBuffer], rax; lpBuffer
0x18006cef5  mov     r9d, 400h; dwLanguageId
0x18006cefb  mov     r8d, ebp; dwMessageId
0x18006cefe  xor     edx, edx; lpSource
0x18006cf00  mov     ecx, 1200h; dwFlags
0x18006cf05  call    cs:__imp_FormatMessageW
0x18006cf0b  lea     rsi, [r14+rsi*2]
0x18006cf0f  mov     r9, [rbx+38h]; unsigned __int16 *
0x18006cf13  mov     rax, [rbx+88h]
0x18006cf1a  mov     rcx, [rbx+80h]
0x18006cf21  mov     rdx, rsi; unsigned __int16 *
0x18006cf24  test    r9, r9
0x18006cf27  jz      short loc_18006CF4B
0x18006cf29  mov     [rsp+278h+Arguments], rax
0x18006cf2e  mov     qword ptr [rsp+278h+nSize], rcx
0x18006cf33  mov     eax, [rbx+40h]
0x18006cf36  mov     dword ptr [rsp+278h+lpBuffer], eax
0x18006cf3a  lea     r8, aHsUHsP; "%hs(%u)\\%hs!%p: "
0x18006cf41  mov     rcx, r14; this
0x18006cf44  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18006cf49  jmp     short loc_18006CF62
0x18006cf4b  mov     [rsp+278h+lpBuffer], rax
0x18006cf50  mov     r9, rcx; unsigned __int16 *
0x18006cf53  lea     r8, aHsP; "%hs!%p: "
0x18006cf5a  mov     rcx, r14; this
0x18006cf5d  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18006cf62  mov     r14, rax
0x18006cf65  mov     r9, [rbx+90h]; unsigned __int16 *
0x18006cf6c  test    r9, r9
0x18006cf6f  jz      short loc_18006CF86
0x18006cf71  lea     r8, aCallerP; "(caller: %p) "
0x18006cf78  mov     rdx, rsi; unsigned __int16 *
0x18006cf7b  mov     rcx, rax; this
0x18006cf7e  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18006cf83  mov     r14, rax
0x18006cf86  call    cs:__imp_GetCurrentThreadId
0x18006cf8c  lea     rcx, [rsp+278h+Buffer]
0x18006cf91  mov     [rsp+278h+var_240], rcx
0x18006cf96  mov     dword ptr [rsp+278h+Arguments], ebp
0x18006cf9a  mov     [rsp+278h+nSize], eax
0x18006cf9e  mov     eax, [rbx+44h]
0x18006cfa1  mov     dword ptr [rsp+278h+lpBuffer], eax
0x18006cfa5  mov     r9, rdi; unsigned __int16 *
0x18006cfa8  lea     r8, aHsDTidX08xWs; "%hs(%d) tid(%x) %08X %ws"
0x18006cfaf  mov     rdx, rsi; unsigned __int16 *
0x18006cfb2  mov     rcx, r14; this
0x18006cfb5  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18006cfba  cmp     qword ptr [rbx+18h], 0
0x18006cfbf  jnz     short loc_18006CFD3
0x18006cfc1  cmp     qword ptr [rbx+48h], 0
0x18006cfc6  jnz     short loc_18006CFD3
0x18006cfc8  cmp     qword ptr [rbx+30h], 0
0x18006cfcd  jz      loc_18006D063
0x18006cfd3  lea     r8, asc_180088B60; "    "
0x18006cfda  mov     rdx, rsi; unsigned __int16 *
0x18006cfdd  mov     rcx, rax; this
0x18006cfe0  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18006cfe5  mov     r9, [rbx+18h]; unsigned __int16 *
0x18006cfe9  test    r9, r9
0x18006cfec  jz      short loc_18006D000
0x18006cfee  lea     r8, aMsgWs; "Msg:[%ws] "
0x18006cff5  mov     rdx, rsi; unsigned __int16 *
0x18006cff8  mov     rcx, rax; this
0x18006cffb  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18006d000  mov     r9, [rbx+48h]; unsigned __int16 *
0x18006d004  test    r9, r9
0x18006d007  jz      short loc_18006D01B
0x18006d009  lea     r8, aCallcontextHs; "CallContext:[%hs] "
0x18006d010  mov     rdx, rsi; unsigned __int16 *
0x18006d013  mov     rcx, rax; this
0x18006d016  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18006d01b  mov     rcx, [rbx+28h]
0x18006d01f  mov     r9, [rbx+30h]; unsigned __int16 *
0x18006d023  mov     rdx, rsi; unsigned __int16 *
0x18006d026  test    rcx, rcx
0x18006d029  jz      short loc_18006D041
0x18006d02b  mov     [rsp+278h+lpBuffer], rcx
0x18006d030  lea     r8, aHsHs; "[%hs(%hs)]\n"
0x18006d037  mov     rcx, rax; this
0x18006d03a  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18006d03f  jmp     short loc_18006D063
0x18006d041  mov     rcx, rax; this
0x18006d044  test    r9, r9
0x18006d047  jz      short loc_18006D057
0x18006d049  lea     r8, aHs; "[%hs]\n"
0x18006d050  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18006d055  jmp     short loc_18006D063
0x18006d057  lea     r8, asc_180088BD8; "\n"
0x18006d05e  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18006d063  xor     eax, eax
0x18006d065  mov     rcx, [rsp+278h+var_38]
0x18006d06d  xor     rcx, rsp; StackCookie
0x18006d070  call    __security_check_cookie
0x18006d075  add     rsp, 250h
0x18006d07c  pop     r14
0x18006d07e  pop     rdi
0x18006d07f  pop     rsi
0x18006d080  pop     rbp
0x18006d081  pop     rbx
0x18006d082  retn
```
