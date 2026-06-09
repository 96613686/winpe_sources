# TraceLoggingValidMsiFileType(ushort const *)

- ea: `0x18000c984`
- end: `0x18000ca50`
- name: `?TraceLoggingValidMsiFileType@@YAXPEBG@Z`
- size: `204`
- prototype: `void __fastcall(wchar_t *Str)`
- caller_count: `1`
- callee_count: `3`
- tags: `installer_update`

## callers

- `0x1800022b0`

## callees

- `0x1800010a8`
- `0x180001138`
- `0x18000c984`

## import_xrefs

- `msvcrt!wcsrchr` at `0x18000c996`
- `msvcrt!wcsrchr` at `0x18000ca04`
- `msvcrt!wcsrchr` at `0x18000c996`
- `msvcrt!wcsrchr` at `0x18000ca04`
- `msvcrt!_wcsicmp` at `0x18000c9b2`
- `msvcrt!_wcsicmp` at `0x18000c9ca`
- `msvcrt!_wcsicmp` at `0x18000c9de`
- `msvcrt!_wcsicmp` at `0x18000c9f2`
- `msvcrt!_wcsicmp` at `0x18000c9b2`
- `msvcrt!_wcsicmp` at `0x18000c9ca`
- `msvcrt!_wcsicmp` at `0x18000c9de`
- `msvcrt!_wcsicmp` at `0x18000c9f2`

## pseudocode

```c
void __fastcall TraceLoggingValidMsiFileType(wchar_t *Str)
{
  wchar_t *v2; // rax
  const wchar_t *v3; // rbx
  __int64 v4; // rdx
  wchar_t *v5; // r8
  __int64 v6; // rcx
  __int64 v7; // r8
  __int64 v8; // r9
  __int64 *v9; // [rsp+48h] [rbp+10h] BYREF

  v2 = wcsrchr(Str, 0x2Eu);
  v3 = v2;
  if ( v2 )
  {
    if ( _wcsicmp(L".msi", v2) )
    {
      if ( _wcsicmp(L".msp", v3) )
      {
        if ( _wcsicmp(L".mst", v3) )
        {
          if ( _wcsicmp(L".crdownload", v3) )
          {
            v5 = wcsrchr(Str, 0x5Cu);
            if ( v5 )
            {
              if ( (unsigned int)dword_180013000 > 4 )
              {
                if ( (unsigned __int8)tlgKeywordOn((unsigned int)dword_180013000, v4, v5) )
                {
                  v9 = (__int64 *)(v7 + 2);
                  _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>>(
                    v6,
                    (unsigned __int8 *)&word_180010AC6,
                    v7,
                    v8,
                    &v9);
                }
              }
            }
          }
        }
      }
    }
  }
}

```

## disassembly

```asm
0x18000c984  mov     [rsp+arg_0], rbx
0x18000c989  push    rdi
0x18000c98a  sub     rsp, 30h
0x18000c98e  mov     edx, 2Eh ; '.'; Ch
0x18000c993  mov     rdi, rcx
0x18000c996  call    cs:__imp_wcsrchr
0x18000c99c  mov     rbx, rax
0x18000c99f  test    rax, rax
0x18000c9a2  jz      loc_18000CA45
0x18000c9a8  mov     rdx, rax; String2
0x18000c9ab  lea     rcx, aMsi; ".msi"
0x18000c9b2  call    cs:__imp__wcsicmp
0x18000c9b8  test    eax, eax
0x18000c9ba  jz      loc_18000CA45
0x18000c9c0  mov     rdx, rbx; String2
0x18000c9c3  lea     rcx, aMsp; ".msp"
0x18000c9ca  call    cs:__imp__wcsicmp
0x18000c9d0  test    eax, eax
0x18000c9d2  jz      short loc_18000CA45
0x18000c9d4  mov     rdx, rbx; String2
0x18000c9d7  lea     rcx, aMst; ".mst"
0x18000c9de  call    cs:__imp__wcsicmp
0x18000c9e4  test    eax, eax
0x18000c9e6  jz      short loc_18000CA45
0x18000c9e8  mov     rdx, rbx; String2
0x18000c9eb  lea     rcx, aCrdownload; ".crdownload"
0x18000c9f2  call    cs:__imp__wcsicmp
0x18000c9f8  test    eax, eax
0x18000c9fa  jz      short loc_18000CA45
0x18000c9fc  mov     edx, 5Ch ; '\'; Ch
0x18000ca01  mov     rcx, rdi; Str
0x18000ca04  call    cs:__imp_wcsrchr
0x18000ca0a  mov     r8, rax
0x18000ca0d  test    rax, rax
0x18000ca10  jz      short loc_18000CA45
0x18000ca12  mov     ecx, cs:dword_180013000
0x18000ca18  cmp     ecx, 4
0x18000ca1b  jbe     short loc_18000CA45
0x18000ca1d  call    _tlgKeywordOn
0x18000ca22  test    al, al
0x18000ca24  jz      short loc_18000CA45
0x18000ca26  lea     rax, [r8+2]
0x18000ca2a  mov     [rsp+38h+arg_8], rax
0x18000ca2f  lea     rdx, word_180010AC6
0x18000ca36  lea     rax, [rsp+38h+arg_8]
0x18000ca3b  mov     [rsp+38h+var_18], rax
0x18000ca40  call    ??$Write@U?$_tlgWrapSz@G@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@G@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<ushort> const &)
0x18000ca45  mov     rbx, [rsp+38h+arg_0]
0x18000ca4a  add     rsp, 30h
0x18000ca4e  pop     rdi
0x18000ca4f  retn
```
