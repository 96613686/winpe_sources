# wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)

- ea: `0x18000eb60`
- end: `0x18000ee22`
- name: `?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z`
- size: `706`
- prototype: `__int64 __fastcall(wil *__hidden this, unsigned __int16 *, unsigned __int64, const struct wil::FailureInfo *)`
- caller_count: `4`
- callee_count: `5`
- tags: ``

## callers

- `0x180009930`
- `0x180009be0`
- `0x180011200`
- `0x1800189a0`

## callees

- `0x1800017b0`
- `0x1800021a8`
- `0x18000eb60`
- `0x180011520`
- `0x180088750`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000ed1e`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000ed1e`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x18000ec97`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x18000ec97`

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
            v8 = (const char *)&qword_18008D018;
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
0x18000eb60  push    rbx
0x18000eb62  push    rbp
0x18000eb63  push    rsi
0x18000eb64  push    rdi
0x18000eb65  push    r14
0x18000eb67  sub     rsp, 250h
0x18000eb6e  mov     rax, cs:__security_cookie
0x18000eb75  xor     rax, rsp
0x18000eb78  mov     [rsp+278h+var_38], rax
0x18000eb80  mov     rbx, r8
0x18000eb83  mov     rsi, rdx
0x18000eb86  mov     r14, rcx
0x18000eb89  xor     eax, eax
0x18000eb8b  test    rdx, rdx
0x18000eb8e  jz      loc_18000EE03
0x18000eb94  test    rcx, rcx
0x18000eb97  jz      loc_18000EE03
0x18000eb9d  mov     [rcx], ax
0x18000eba0  mov     rax, cs:g_pfnResultLoggingCallback
0x18000eba7  test    rax, rax
0x18000ebaa  jz      short loc_18000EBCF
0x18000ebac  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, 0; bool wil::details::g_resultMessageCallbackSet
0x18000ebb3  jz      short loc_18000EBCF
0x18000ebb5  mov     r8, rdx
0x18000ebb8  mov     rdx, rcx
0x18000ebbb  mov     rcx, rbx
0x18000ebbe  call    cs:__guard_dispatch_icall_fptr
0x18000ebc4  cmp     word ptr [r14], 0
0x18000ebc9  jnz     loc_18000EE01
0x18000ebcf  mov     ecx, [rbx]
0x18000ebd1  test    ecx, ecx
0x18000ebd3  jz      short loc_18000EC26
0x18000ebd5  sub     ecx, 1
0x18000ebd8  jz      short loc_18000EC0E
0x18000ebda  sub     ecx, 1
0x18000ebdd  jz      short loc_18000EBF6
0x18000ebdf  cmp     ecx, 1
0x18000ebe2  jz      short loc_18000EBED
0x18000ebe4  lea     rdi, qword_18008D018
0x18000ebeb  jmp     short loc_18000EC2D
0x18000ebed  lea     rdi, aFailfast; "FailFast"
0x18000ebf4  jmp     short loc_18000EC2D
0x18000ebf6  test    byte ptr [rbx+4], 8
0x18000ebfa  lea     rax, aLoghr; "LogHr"
0x18000ec01  lea     rdi, aLognt; "LogNt"
0x18000ec08  cmovz   rdi, rax
0x18000ec0c  jmp     short loc_18000EC2D
0x18000ec0e  test    byte ptr [rbx+4], 8
0x18000ec12  lea     rax, aReturnhr; "ReturnHr"
0x18000ec19  lea     rdi, aReturnnt; "ReturnNt"
0x18000ec20  cmovz   rdi, rax
0x18000ec24  jmp     short loc_18000EC2D
0x18000ec26  lea     rdi, aException; "Exception"
0x18000ec2d  xor     edx, edx; Val
0x18000ec2f  mov     r8d, 200h; Size
0x18000ec35  lea     rcx, [rsp+278h+Buffer]; void *
0x18000ec3a  call    memset_0
0x18000ec3f  test    byte ptr [rbx+4], 8
0x18000ec43  jz      short loc_18000EC69
0x18000ec45  mov     ebp, [rbx+0Ch]
0x18000ec48  mov     rax, cs:?g_pfnFormatNtStatusMsg@details@wil@@3P6AXJPEAGK@ZEA; void (*wil::details::g_pfnFormatNtStatusMsg)(long,ushort *,ulong)
0x18000ec4f  test    rax, rax
0x18000ec52  jz      short loc_18000ECA3
0x18000ec54  mov     r8d, 100h
0x18000ec5a  lea     rdx, [rsp+278h+Buffer]
0x18000ec5f  mov     ecx, ebp
0x18000ec61  call    cs:__guard_dispatch_icall_fptr
0x18000ec67  jmp     short loc_18000ECA3
0x18000ec69  mov     ebp, [rbx+8]
0x18000ec6c  mov     [rsp+278h+Arguments], 0; Arguments
0x18000ec75  mov     [rsp+278h+nSize], 100h; nSize
0x18000ec7d  lea     rax, [rsp+278h+Buffer]
0x18000ec82  mov     [rsp+278h+lpBuffer], rax; lpBuffer
0x18000ec87  mov     r9d, 400h; dwLanguageId
0x18000ec8d  mov     r8d, ebp; dwMessageId
0x18000ec90  xor     edx, edx; lpSource
0x18000ec92  mov     ecx, 1200h; dwFlags
0x18000ec97  call    cs:__imp_FormatMessageW
0x18000ec9e  nop     dword ptr [rax+rax+00h]
0x18000eca3  lea     rsi, [r14+rsi*2]
0x18000eca7  mov     r9, [rbx+38h]; unsigned __int16 *
0x18000ecab  mov     rax, [rbx+88h]
0x18000ecb2  mov     rcx, [rbx+80h]
0x18000ecb9  mov     rdx, rsi; unsigned __int16 *
0x18000ecbc  test    r9, r9
0x18000ecbf  jz      short loc_18000ECE3
0x18000ecc1  mov     [rsp+278h+Arguments], rax
0x18000ecc6  mov     qword ptr [rsp+278h+nSize], rcx
0x18000eccb  mov     eax, [rbx+40h]
0x18000ecce  mov     dword ptr [rsp+278h+lpBuffer], eax
0x18000ecd2  lea     r8, aHsUHsP; "%hs(%u)\\%hs!%p: "
0x18000ecd9  mov     rcx, r14; this
0x18000ecdc  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18000ece1  jmp     short loc_18000ECFA
0x18000ece3  mov     [rsp+278h+lpBuffer], rax
0x18000ece8  mov     r9, rcx; unsigned __int16 *
0x18000eceb  lea     r8, aHsP; "%hs!%p: "
0x18000ecf2  mov     rcx, r14; this
0x18000ecf5  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18000ecfa  mov     r14, rax
0x18000ecfd  mov     r9, [rbx+90h]; unsigned __int16 *
0x18000ed04  test    r9, r9
0x18000ed07  jz      short loc_18000ED1E
0x18000ed09  lea     r8, aCallerP; "(caller: %p) "
0x18000ed10  mov     rdx, rsi; unsigned __int16 *
0x18000ed13  mov     rcx, rax; this
0x18000ed16  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18000ed1b  mov     r14, rax
0x18000ed1e  call    cs:__imp_GetCurrentThreadId
0x18000ed25  nop     dword ptr [rax+rax+00h]
0x18000ed2a  lea     rcx, [rsp+278h+Buffer]
0x18000ed2f  mov     [rsp+278h+var_240], rcx
0x18000ed34  mov     dword ptr [rsp+278h+Arguments], ebp
0x18000ed38  mov     [rsp+278h+nSize], eax
0x18000ed3c  mov     eax, [rbx+44h]
0x18000ed3f  mov     dword ptr [rsp+278h+lpBuffer], eax
0x18000ed43  mov     r9, rdi; unsigned __int16 *
0x18000ed46  lea     r8, aHsDTidX08xWs; "%hs(%d) tid(%x) %08X %ws"
0x18000ed4d  mov     rdx, rsi; unsigned __int16 *
0x18000ed50  mov     rcx, r14; this
0x18000ed53  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18000ed58  cmp     qword ptr [rbx+18h], 0
0x18000ed5d  jnz     short loc_18000ED71
0x18000ed5f  cmp     qword ptr [rbx+48h], 0
0x18000ed64  jnz     short loc_18000ED71
0x18000ed66  cmp     qword ptr [rbx+30h], 0
0x18000ed6b  jz      loc_18000EE01
0x18000ed71  lea     r8, asc_18008D120; "    "
0x18000ed78  mov     rdx, rsi; unsigned __int16 *
0x18000ed7b  mov     rcx, rax; this
0x18000ed7e  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18000ed83  mov     r9, [rbx+18h]; unsigned __int16 *
0x18000ed87  test    r9, r9
0x18000ed8a  jz      short loc_18000ED9E
0x18000ed8c  lea     r8, aMsgWs; "Msg:[%ws] "
0x18000ed93  mov     rdx, rsi; unsigned __int16 *
0x18000ed96  mov     rcx, rax; this
0x18000ed99  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18000ed9e  mov     r9, [rbx+48h]; unsigned __int16 *
0x18000eda2  test    r9, r9
0x18000eda5  jz      short loc_18000EDB9
0x18000eda7  lea     r8, aCallcontextHs; "CallContext:[%hs] "
0x18000edae  mov     rdx, rsi; unsigned __int16 *
0x18000edb1  mov     rcx, rax; this
0x18000edb4  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18000edb9  mov     rcx, [rbx+28h]
0x18000edbd  mov     r9, [rbx+30h]; unsigned __int16 *
0x18000edc1  mov     rdx, rsi; unsigned __int16 *
0x18000edc4  test    rcx, rcx
0x18000edc7  jz      short loc_18000EDDF
0x18000edc9  mov     [rsp+278h+lpBuffer], rcx
0x18000edce  lea     r8, aHsHs; "[%hs(%hs)]\n"
0x18000edd5  mov     rcx, rax; this
0x18000edd8  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18000eddd  jmp     short loc_18000EE01
0x18000eddf  mov     rcx, rax; this
0x18000ede2  test    r9, r9
0x18000ede5  jz      short loc_18000EDF5
0x18000ede7  lea     r8, aHs; "[%hs]\n"
0x18000edee  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18000edf3  jmp     short loc_18000EE01
0x18000edf5  lea     r8, asc_18008D198; "\n"
0x18000edfc  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18000ee01  xor     eax, eax
0x18000ee03  mov     rcx, [rsp+278h+var_38]
0x18000ee0b  xor     rcx, rsp; StackCookie
0x18000ee0e  call    __security_check_cookie
0x18000ee13  add     rsp, 250h
0x18000ee1a  pop     r14
0x18000ee1c  pop     rdi
0x18000ee1d  pop     rsi
0x18000ee1e  pop     rbp
0x18000ee1f  pop     rbx
0x18000ee20  retn
```
