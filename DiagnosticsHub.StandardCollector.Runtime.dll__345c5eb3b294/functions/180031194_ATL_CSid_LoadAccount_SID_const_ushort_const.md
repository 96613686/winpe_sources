# ATL::CSid::LoadAccount(_SID const *,ushort const *)

- ea: `0x180031194`
- end: `0x180031261`
- name: `?LoadAccount@CSid@ATL@@QEAA_NPEBU_SID@@PEBG@Z`
- size: `205`
- prototype: `bool(ATL::CSid *__hidden this, const struct _SID *, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `5`
- tags: `authz_impersonation`

## callers

- `0x180031284`

## callees

- `0x180002034`
- `0x1800020bc`
- `0x180002604`
- `0x180031194`
- `0x18003151c`

## import_xrefs

- `ADVAPI32!GetLengthSid` at `0x180031200`
- `ADVAPI32!GetLengthSid` at `0x180031200`
- `ADVAPI32!CopySid` at `0x18003121b`
- `ADVAPI32!CopySid` at `0x18003121b`
- `ADVAPI32!IsValidSid` at `0x1800311f3`
- `ADVAPI32!IsValidSid` at `0x1800311f3`

## pseudocode

```c
bool __fastcall ATL::CSid::LoadAccount(ATL::CSid *this, struct _SID *a2, const unsigned __int16 *a3)
{
  DWORD LengthSid; // eax
  bool result; // al
  int Error; // eax

  *((_DWORD *)this + 20) = 7;
  ATL::CSimpleStringT<unsigned short,0>::Empty((char *)this + 88);
  ATL::CSimpleStringT<unsigned short,0>::Empty((char *)this + 96);
  ATL::CSimpleStringT<unsigned short,0>::Empty((char *)this + 104);
  ATL::CSimpleStringT<unsigned short,0>::Empty((char *)this + 112);
  try
  {
    *((_BYTE *)this + 76) = 0;
    if ( a2 )
    {
      ATL::CSimpleStringT<unsigned short,0>::SetString((char *)this + 112, 0, 0);
      if ( !IsValidSid(a2) )
        ATL::AtlThrowImpl(-2147024809);
      LengthSid = GetLengthSid(a2);
      if ( LengthSid > 0x44 )
        ATL::AtlThrowImpl(-2147024809);
      _mm_lfence();
      *((_BYTE *)this + 76) = 1;
      if ( !CopySid(LengthSid, (char *)this + 8, a2) )
      {
        Error = ATL::AtlHresultFromLastError();
        *((_BYTE *)this + 76) = 0;
        ATL::AtlThrowImpl(Error);
      }
      result = 1;
    }
    else
    {
      result = 0;
    }
  }
  catch ( ... )
  {
    ATL::CSid::Clear(this);
    throw;
  }
  return result;
}

```

## disassembly

```asm
0x180031194  mov     [rsp+arg_8], rbx
0x180031199  mov     [rsp+arg_10], rsi
0x18003119e  mov     [rsp+arg_0], rcx
0x1800311a3  push    rdi
0x1800311a4  sub     rsp, 20h
0x1800311a8  mov     rdi, rdx
0x1800311ab  mov     rbx, rcx
0x1800311ae  mov     dword ptr [rcx+50h], 7
0x1800311b5  add     rcx, 58h ; 'X'
0x1800311b9  call    ?Empty@?$CSimpleStringT@G$0A@@ATL@@QEAAXXZ; ATL::CSimpleStringT<ushort,0>::Empty(void)
0x1800311be  lea     rcx, [rbx+60h]
0x1800311c2  call    ?Empty@?$CSimpleStringT@G$0A@@ATL@@QEAAXXZ; ATL::CSimpleStringT<ushort,0>::Empty(void)
0x1800311c7  lea     rcx, [rbx+68h]
0x1800311cb  call    ?Empty@?$CSimpleStringT@G$0A@@ATL@@QEAAXXZ; ATL::CSimpleStringT<ushort,0>::Empty(void)
0x1800311d0  lea     rcx, [rbx+70h]
0x1800311d4  call    ?Empty@?$CSimpleStringT@G$0A@@ATL@@QEAAXXZ; ATL::CSimpleStringT<ushort,0>::Empty(void)
0x1800311d9  mov     byte ptr [rbx+4Ch], 0
0x1800311dd  test    rdi, rdi
0x1800311e0  jz      short loc_180031229
0x1800311e2  xor     r8d, r8d
0x1800311e5  xor     edx, edx
0x1800311e7  lea     rcx, [rbx+70h]
0x1800311eb  call    ?SetString@?$CSimpleStringT@G$0A@@ATL@@QEAAXPEBGH@Z; ATL::CSimpleStringT<ushort,0>::SetString(ushort const *,int)
0x1800311f0  mov     rcx, rdi; pSid
0x1800311f3  call    cs:__imp_IsValidSid
0x1800311f9  test    eax, eax
0x1800311fb  jz      short loc_18003123B
0x1800311fd  mov     rcx, rdi; pSid
0x180031200  call    cs:__imp_GetLengthSid
0x180031206  cmp     eax, 44h ; 'D'
0x180031209  ja      short loc_180031245
0x18003120b  lfence
0x18003120e  mov     byte ptr [rbx+4Ch], 1
0x180031212  lea     rdx, [rbx+8]; pDestinationSid
0x180031216  mov     r8, rdi; pSourceSid
0x180031219  mov     ecx, eax; nDestinationSidLength
0x18003121b  call    cs:__imp_CopySid
0x180031221  test    eax, eax
0x180031223  jz      short loc_18003124F
0x180031225  mov     al, 1
0x180031227  jmp     short loc_18003122B
0x180031229  xor     al, al
0x18003122b  mov     rbx, [rsp+28h+arg_8]
0x180031230  mov     rsi, [rsp+28h+arg_10]
0x180031235  add     rsp, 20h
0x180031239  pop     rdi
0x18003123a  retn
0x18003123b  mov     ecx, 80070057h; int
0x180031240  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x180031245  mov     ecx, 80070057h; int
0x18003124a  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x18003124f  call    ?AtlHresultFromLastError@ATL@@YAJXZ; ATL::AtlHresultFromLastError(void)
0x180031254  mov     byte ptr [rbx+4Ch], 0
0x180031258  mov     ecx, eax; int
0x18003125a  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
```
