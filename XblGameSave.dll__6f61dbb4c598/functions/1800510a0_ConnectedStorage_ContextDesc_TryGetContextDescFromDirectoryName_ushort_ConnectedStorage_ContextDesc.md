# ConnectedStorage::ContextDesc::TryGetContextDescFromDirectoryName(ushort *,ConnectedStorage::ContextDesc *)

- ea: `0x1800510a0`
- end: `0x1800512ac`
- name: `?TryGetContextDescFromDirectoryName@ContextDesc@ConnectedStorage@@SA_NPEAGPEAV12@@Z`
- size: `524`
- prototype: `bool __fastcall(unsigned __int16 *, struct ConnectedStorage::ContextDesc *)`
- caller_count: `2`
- callee_count: `10`
- tags: ``

## callers

- `0x18002f6b8`
- `0x18003373c`

## callees

- `0x180003c70`
- `0x18000ab18`
- `0x18000b67c`
- `0x180011c0c`
- `0x180012ed8`
- `0x18001cedc`
- `0x180050da0`
- `0x180050ddc`
- `0x1800510a0`
- `0x1800512b4`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcstoui64` at `0x18005114d`
- `api-ms-win-crt-private-l1-1-0!_o__wcstoui64` at `0x18005114d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180051196`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800511a6`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18005122b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18005123b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180051196`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800511a6`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18005122b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18005123b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18005113e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18005113e`

## pseudocode

```c
// Hidden C++ exception states: #wind=2 #try_helpers=1
char __fastcall ConnectedStorage::ContextDesc::TryGetContextDescFromDirectoryName(
        unsigned __int16 *a1,
        HSTRING *a2,
        const unsigned __int16 *a3)
{
  unsigned __int16 *v6; // rax
  const unsigned __int16 *v7; // r8
  unsigned __int16 *v8; // rdi
  __int64 v9; // rdx
  HSTRING *v10; // rax
  PCWSTR StringRawBuffer; // rax
  __int64 v12; // rax
  unsigned __int16 v13; // dx
  const unsigned __int16 *v14; // r8
  const unsigned __int16 *v15; // r8
  __int64 v16; // rdx
  HSTRING *v17; // rdx
  HSTRING string; // [rsp+20h] [rbp-B8h] BYREF
  HSTRING v19[11]; // [rsp+28h] [rbp-B0h] BYREF
  WCHAR sourceString[24]; // [rsp+80h] [rbp-58h] BYREF

  v19[1] = (HSTRING)a1;
  if ( *a1 )
  {
    v6 = wcschr(a1, (unsigned __int16)a2);
    if ( v6 && *v6 && (v8 = v6 + 1, v6[1]) )
    {
      v9 = v6 - a1;
      if ( (unsigned int)(v9 - 1) > 0x102 )
      {
        ConnectedStorage::ReportErrorNoThrow(
          (ConnectedStorage *)0x8083200ALL,
          (int)L"Malformed filename - missing or too long xuid",
          v7);
        return 0;
      }
      else
      {
        v10 = ConnectedStorage::SimpleHStringWrapper::SimpleHStringWrapper(v19, v9, a1);
        StringRawBuffer = WindowsGetStringRawBuffer(*v10, 0);
        v12 = _o__wcstoui64(StringRawBuffer, 0, 16);
        StringCchPrintfW(sourceString, 0x15u, L"%I64u", v12);
        ConnectedStorage::SimpleHStringWrapper::SimpleHStringWrapper(&string, sourceString);
        ConnectedStorage::SimpleHStringWrapper::operator=(a2 + 2);
        WindowsDeleteString(string);
        string = 0;
        WindowsDeleteString(v19[0]);
        if ( *v8 )
        {
          if ( wcschr(v8, v13) )
          {
            ConnectedStorage::ReportErrorNoThrow(
              (ConnectedStorage *)0x8083200ALL,
              (int)L"Malformed filename - scid has _'s",
              v15);
            return 0;
          }
          else
          {
            v16 = -1;
            do
              ++v16;
            while ( v8[v16] );
            v17 = ConnectedStorage::SimpleHStringWrapper::SimpleHStringWrapper(v19, v16, v8);
            ConnectedStorage::ContextDesc::ExtractUnstrippedScid(&string, v17);
            ConnectedStorage::SimpleHStringWrapper::operator=(a2 + 3);
            WindowsDeleteString(string);
            string = 0;
            WindowsDeleteString(v19[0]);
            *((_BYTE *)a2 + 44) = 0;
            return 1;
          }
        }
        else
        {
          ConnectedStorage::ReportErrorNoThrow(
            (ConnectedStorage *)0x8083200ALL,
            (int)L"Malformed filename - no scid",
            v14);
          return 0;
        }
      }
    }
    else
    {
      ConnectedStorage::ReportErrorNoThrow((ConnectedStorage *)0x8083200ALL, (int)L"Malformed filename - no scid", v7);
      return 0;
    }
  }
  else
  {
    ConnectedStorage::ReportErrorNoThrow(
      (ConnectedStorage *)0x8083200ALL,
      (int)L"Malformed filename - no xuid/scid",
      a3);
    return 0;
  }
}

```

## disassembly

```asm
0x1800510a0  mov     [rsp+arg_10], rbx
0x1800510a5  push    rsi
0x1800510a6  push    rdi
0x1800510a7  push    r14
0x1800510a9  sub     rsp, 0C0h
0x1800510b0  mov     rax, cs:__security_cookie
0x1800510b7  xor     rax, rsp
0x1800510ba  mov     [rsp+0D8h+var_28], rax
0x1800510c2  mov     rsi, rdx
0x1800510c5  mov     rbx, rcx
0x1800510c8  mov     [rsp+0D8h+var_A8], rcx
0x1800510cd  xor     r14d, r14d
0x1800510d0  cmp     [rcx], r14w
0x1800510d4  jnz     short loc_1800510EE
0x1800510d6  lea     rdx, aMalformedFilen_1; "Malformed filename - no xuid/scid"
0x1800510dd  mov     ecx, 8083200Ah; this
0x1800510e2  call    ?ReportErrorNoThrow@ConnectedStorage@@YAXJPEBG@Z; ConnectedStorage::ReportErrorNoThrow(long,ushort const *)
0x1800510e7  xor     al, al
0x1800510e9  jmp     loc_180051287
0x1800510ee  call    ?wcschr@@YAPEAGPEAGG@Z; wcschr(ushort *,ushort)
0x1800510f3  mov     rdx, rax
0x1800510f6  test    rax, rax
0x1800510f9  jz      loc_18005125E
0x1800510ff  cmp     [rax], r14w
0x180051103  jz      loc_18005125E
0x180051109  lea     rdi, [rax+2]
0x18005110d  cmp     [rdi], r14w
0x180051111  jz      loc_18005125E
0x180051117  sub     rdx, rbx
0x18005111a  sar     rdx, 1; unsigned int
0x18005111d  lea     eax, [rdx-1]
0x180051120  cmp     eax, 102h
0x180051125  ja      loc_180051249
0x18005112b  mov     r8, rbx; unsigned __int16 *
0x18005112e  lea     rcx, [rsp+0D8h+var_B0]; string
0x180051133  call    ??0SimpleHStringWrapper@ConnectedStorage@@QEAA@IPEBG@Z; ConnectedStorage::SimpleHStringWrapper::SimpleHStringWrapper(uint,ushort const *)
0x180051138  nop
0x180051139  xor     edx, edx; length
0x18005113b  mov     rcx, [rax]; string
0x18005113e  call    cs:__imp_WindowsGetStringRawBuffer
0x180051144  xor     edx, edx
0x180051146  lea     r8d, [rdx+10h]
0x18005114a  mov     rcx, rax
0x18005114d  call    cs:__imp__o__wcstoui64
0x180051153  mov     r9, rax
0x180051156  lea     r8, aI64u; "%I64u"
0x18005115d  mov     edx, 15h; unsigned __int64
0x180051162  lea     rcx, [rsp+0D8h+sourceString]; unsigned __int16 *
0x18005116a  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18005116f  lea     rdx, [rsp+0D8h+sourceString]; sourceString
0x180051177  lea     rcx, [rsp+0D8h+string]; string
0x18005117c  call    ??0SimpleHStringWrapper@ConnectedStorage@@QEAA@PEBG@Z; ConnectedStorage::SimpleHStringWrapper::SimpleHStringWrapper(ushort const *)
0x180051181  nop
0x180051182  lea     rcx, [rsi+10h]; newString
0x180051186  lea     rdx, [rsp+0D8h+string]
0x18005118b  call    ??4SimpleHStringWrapper@ConnectedStorage@@QEAAAEAV01@AEBV01@@Z; ConnectedStorage::SimpleHStringWrapper::operator=(ConnectedStorage::SimpleHStringWrapper const &)
0x180051190  nop
0x180051191  mov     rcx, [rsp+0D8h+string]; string
0x180051196  call    cs:__imp_WindowsDeleteString
0x18005119c  mov     [rsp+0D8h+string], r14
0x1800511a1  mov     rcx, [rsp+0D8h+var_B0]; string
0x1800511a6  call    cs:__imp_WindowsDeleteString
0x1800511ac  cmp     [rdi], r14w
0x1800511b0  jnz     short loc_1800511CA
0x1800511b2  lea     rdx, aMalformedFilen; "Malformed filename - no scid"
0x1800511b9  mov     ecx, 8083200Ah; this
0x1800511be  call    ?ReportErrorNoThrow@ConnectedStorage@@YAXJPEBG@Z; ConnectedStorage::ReportErrorNoThrow(long,ushort const *)
0x1800511c3  xor     al, al
0x1800511c5  jmp     loc_180051287
0x1800511ca  mov     rcx, rdi; unsigned __int16 *
0x1800511cd  call    ?wcschr@@YAPEAGPEAGG@Z; wcschr(ushort *,ushort)
0x1800511d2  test    rax, rax
0x1800511d5  jz      short loc_1800511EF
0x1800511d7  lea     rdx, aMalformedFilen_2; "Malformed filename - scid has _'s"
0x1800511de  mov     ecx, 8083200Ah; this
0x1800511e3  call    ?ReportErrorNoThrow@ConnectedStorage@@YAXJPEBG@Z; ConnectedStorage::ReportErrorNoThrow(long,ushort const *)
0x1800511e8  xor     al, al
0x1800511ea  jmp     loc_180051287
0x1800511ef  or      rdx, 0FFFFFFFFFFFFFFFFh
0x1800511f3  inc     rdx; unsigned int
0x1800511f6  cmp     [rdi+rdx*2], r14w
0x1800511fb  jnz     short loc_1800511F3
0x1800511fd  mov     r8, rdi; unsigned __int16 *
0x180051200  lea     rcx, [rsp+0D8h+var_B0]; string
0x180051205  call    ??0SimpleHStringWrapper@ConnectedStorage@@QEAA@IPEBG@Z; ConnectedStorage::SimpleHStringWrapper::SimpleHStringWrapper(uint,ushort const *)
0x18005120a  nop
0x18005120b  mov     rdx, rax
0x18005120e  lea     rcx, [rsp+0D8h+string]
0x180051213  call    ?ExtractUnstrippedScid@ContextDesc@ConnectedStorage@@CA?AVSimpleHStringWrapper@2@AEBV32@@Z; ConnectedStorage::ContextDesc::ExtractUnstrippedScid(ConnectedStorage::SimpleHStringWrapper const &)
0x180051218  nop
0x180051219  lea     rcx, [rsi+18h]; newString
0x18005121d  mov     rdx, rax
0x180051220  call    ??4SimpleHStringWrapper@ConnectedStorage@@QEAAAEAV01@AEBV01@@Z; ConnectedStorage::SimpleHStringWrapper::operator=(ConnectedStorage::SimpleHStringWrapper const &)
0x180051225  nop
0x180051226  mov     rcx, [rsp+0D8h+string]; string
0x18005122b  call    cs:__imp_WindowsDeleteString
0x180051231  mov     [rsp+0D8h+string], r14
0x180051236  mov     rcx, [rsp+0D8h+var_B0]; string
0x18005123b  call    cs:__imp_WindowsDeleteString
0x180051241  mov     [rsi+2Ch], r14b
0x180051245  mov     al, 1
0x180051247  jmp     short loc_180051287
0x180051249  lea     rdx, aMalformedFilen_0; "Malformed filename - missing or too lon"...
0x180051250  mov     ecx, 8083200Ah; this
0x180051255  call    ?ReportErrorNoThrow@ConnectedStorage@@YAXJPEBG@Z; ConnectedStorage::ReportErrorNoThrow(long,ushort const *)
0x18005125a  xor     al, al
0x18005125c  jmp     short loc_180051287
0x18005125e  lea     rdx, aMalformedFilen; "Malformed filename - no scid"
0x180051265  mov     ecx, 8083200Ah; this
0x18005126a  call    ?ReportErrorNoThrow@ConnectedStorage@@YAXJPEBG@Z; ConnectedStorage::ReportErrorNoThrow(long,ushort const *)
0x18005126f  xor     al, al
0x180051271  jmp     short loc_180051287
0x180051273  jmp     short loc_180051277
0x180051275  jmp     short $+2
0x180051277  mov     edx, dword ptr [rsp+0D8h+string]; unsigned __int16 *
0x18005127b  mov     rcx, [rsp+0D8h+var_A8]; this
0x180051280  call    ?EventWriteBadContextDirectory@ConnectedStorage@@YAXQEBGI@Z; ConnectedStorage::EventWriteBadContextDirectory(ushort const * const,uint)
0x180051285  xor     al, al
0x180051287  mov     rcx, [rsp+0D8h+var_28]
0x18005128f  xor     rcx, rsp; StackCookie
0x180051292  call    __security_check_cookie
0x180051297  mov     rbx, [rsp+0D8h+arg_10]
0x18005129f  add     rsp, 0C0h
0x1800512a6  pop     r14
0x1800512a8  pop     rdi
0x1800512a9  pop     rsi
0x1800512aa  retn
```
