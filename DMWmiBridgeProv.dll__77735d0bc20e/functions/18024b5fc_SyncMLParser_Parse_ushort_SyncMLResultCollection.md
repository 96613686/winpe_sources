# SyncMLParser::Parse(ushort *,SyncMLResultCollection &)

- ea: `0x18024b5fc`
- end: `0x18024b8ac`
- name: `?Parse@SyncMLParser@@QEAAJPEAGAEAVSyncMLResultCollection@@@Z`
- size: `688`
- prototype: `int(SyncMLParser *__hidden this, unsigned __int16 *, struct SyncMLResultCollection *)`
- caller_count: `2`
- callee_count: `7`
- tags: `registry_config`

## callers

- `0x180240ae0`
- `0x18024c418`

## callees

- `0x180001308`
- `0x180243280`
- `0x180246950`
- `0x180246c68`
- `0x180246e88`
- `0x18024b5fc`
- `0x18024f010`

## import_xrefs

- `SHLWAPI!__imp_SHCreateMemStream` at `0x18024b67d`
- `SHLWAPI!__imp_SHCreateMemStream` at `0x18024b67d`
- `XmlLite!CreateXmlReader` at `0x18024b6a3`
- `XmlLite!CreateXmlReader` at `0x18024b6a3`
- `XmlLite!CreateXmlReaderInputWithEncodingName` at `0x18024b6f5`
- `XmlLite!CreateXmlReaderInputWithEncodingName` at `0x18024b6f5`

## pseudocode

```c
__int64 __fastcall SyncMLParser::Parse(SyncMLParser *this, unsigned __int16 *a2, struct SyncMLResultCollection *a3)
{
  IStream *v3; // rdi
  __int64 v6; // rcx
  int v7; // r8d
  int v8; // r9d
  HRESULT v9; // ebx
  int started; // eax
  HRESULT v11; // eax
  bool v12; // sf
  void *ppvObject; // [rsp+30h] [rbp-20h] BYREF
  unsigned __int16 *v15; // [rsp+38h] [rbp-18h] BYREF
  IXmlReaderInput *ppInput; // [rsp+40h] [rbp-10h] BYREF
  const char *v17; // [rsp+48h] [rbp-8h] BYREF
  int v18; // [rsp+80h] [rbp+30h] BYREF
  int v19; // [rsp+84h] [rbp+34h]
  int v20; // [rsp+88h] [rbp+38h] BYREF
  unsigned __int64 v21; // [rsp+98h] [rbp+48h] BYREF

  v19 = HIDWORD(this);
  v3 = 0;
  ppvObject = 0;
  ppInput = 0;
  v20 = 0;
  v21 = 0;
  v15 = 0;
  v18 = 0;
  SyncMLResultCollection::Clear(a3);
  if ( a2 )
  {
    v9 = StringCchLengthW(a2, 0x7FFFFFFFu, &v21);
    if ( v9 >= 0 )
    {
      v17 = 0;
      if ( is_mul_ok(v21, 2u) )
      {
        v3 = SHCreateMemStream((const BYTE *)a2, 2 * (int)v21);
        if ( v3 )
        {
          v9 = CreateXmlReader(&GUID_7279fc81_709d_4095_b63d_69fe4b0d9030, &ppvObject, 0);
          if ( v9 >= 0 )
          {
            v9 = (*(__int64 (__fastcall **)(void *, __int64))(*(_QWORD *)ppvObject + 40LL))(ppvObject, 4);
            if ( v9 >= 0 )
            {
              v9 = CreateXmlReaderInputWithEncodingName((IUnknown *)v3, 0, L"UTF-16", 0, 0, &ppInput);
              if ( v9 >= 0 )
              {
                started = (*(__int64 (__fastcall **)(void *, IXmlReaderInput *))(*(_QWORD *)ppvObject + 24LL))(
                            ppvObject,
                            ppInput);
LABEL_17:
                while ( 1 )
                {
                  v9 = started;
                  v12 = started < 0;
LABEL_18:
                  if ( v12 )
                    break;
                  do
                  {
                    while ( 1 )
                    {
                      v11 = (*(__int64 (__fastcall **)(void *, int *))(*(_QWORD *)ppvObject + 48LL))(ppvObject, &v20);
                      v9 = v11;
                      if ( v11 )
                      {
                        if ( v11 == 1 )
                          v9 = 0;
                        goto LABEL_30;
                      }
                      if ( v20 == 1 )
                        break;
                      if ( v20 == 3 )
                      {
                        v9 = (*(__int64 (__fastcall **)(void *, unsigned __int16 **, int *))(*(_QWORD *)ppvObject + 128LL))(
                               ppvObject,
                               &v15,
                               &v18);
                        if ( v9 < 0 )
                          goto LABEL_30;
                        v6 = *((_QWORD *)a3 + 6);
                        v9 = 0;
                        if ( v6 )
                          v9 = (*(__int64 (__fastcall **)(__int64, unsigned __int16 *))(*(_QWORD *)v6 + 24LL))(v6, v15);
                        v12 = v9 < 0;
                        goto LABEL_18;
                      }
                      if ( v20 == 15 )
                      {
                        v9 = (*(__int64 (__fastcall **)(void *, unsigned __int16 **, int *))(*(_QWORD *)ppvObject + 112LL))(
                               ppvObject,
                               &v15,
                               &v18);
                        if ( v9 < 0 )
                          goto LABEL_30;
                        started = SyncMLResultCollection::HandleEndElement(a3, v15);
                        goto LABEL_17;
                      }
                    }
                  }
                  while ( (*(unsigned int (__fastcall **)(void *))(*(_QWORD *)ppvObject + 160LL))(ppvObject) );
                  v9 = (*(__int64 (__fastcall **)(void *, unsigned __int16 **, int *))(*(_QWORD *)ppvObject + 112LL))(
                         ppvObject,
                         &v15,
                         &v18);
                  if ( v9 < 0 )
                    break;
                  started = SyncMLResultCollection::HandleStartElement(a3, v15);
                }
              }
            }
          }
        }
        else
        {
          v9 = -2147024882;
        }
      }
      else
      {
        v9 = -2147024362;
      }
    }
  }
  else
  {
    v9 = -2147024809;
  }
LABEL_30:
  if ( (unsigned int)dword_180380B68 > 4 )
  {
    LODWORD(v21) = v9;
    v17 = "Parse";
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
      v6,
      (unsigned int)byte_180370E35,
      v7,
      v8,
      (__int64)&v17,
      (__int64)&v21);
  }
  if ( ppvObject )
  {
    (*(void (__fastcall **)(void *))(*(_QWORD *)ppvObject + 16LL))(ppvObject);
    ppvObject = 0;
  }
  if ( v3 )
    ((void (__fastcall *)(IStream *))v3->lpVtbl->Release)(v3);
  if ( ppInput )
    ((void (__fastcall *)(IXmlReaderInput *))ppInput->lpVtbl->Release)(ppInput);
  return (unsigned int)v9;
}

```

## disassembly

```asm
0x18024b5fc  mov     [rsp-28h+arg_0], rcx
0x18024b601  push    rbp
0x18024b602  push    rbx
0x18024b603  push    rsi
0x18024b604  push    rdi
0x18024b605  push    r14
0x18024b607  mov     rbp, rsp
0x18024b60a  sub     rsp, 50h
0x18024b60e  xor     edi, edi
0x18024b610  mov     [rbp+ppvObject], 0
0x18024b618  mov     rcx, r8; this
0x18024b61b  mov     [rbp+var_10], rdi
0x18024b61f  mov     [rbp+arg_8], edi
0x18024b622  mov     r14, r8
0x18024b625  mov     [rbp+arg_18], rdi
0x18024b629  mov     rsi, rdx
0x18024b62c  mov     [rbp+var_18], rdi
0x18024b630  mov     dword ptr [rbp+arg_0], edi
0x18024b633  call    ?Clear@SyncMLResultCollection@@QEAAXXZ; SyncMLResultCollection::Clear(void)
0x18024b638  test    rsi, rsi
0x18024b63b  jnz     short loc_18024B647
0x18024b63d  mov     ebx, 80070057h
0x18024b642  jmp     loc_18024B822
0x18024b647  lea     r8, [rbp+arg_18]; unsigned __int64 *
0x18024b64b  mov     edx, 7FFFFFFFh; unsigned __int64
0x18024b650  mov     rcx, rsi; unsigned __int16 *
0x18024b653  call    ?StringCchLengthW@@YAJPEBG_KPEA_K@Z; StringCchLengthW(ushort const *,unsigned __int64,unsigned __int64 *)
0x18024b658  mov     ebx, eax
0x18024b65a  test    eax, eax
0x18024b65c  js      loc_18024B822
0x18024b662  mov     eax, 2
0x18024b667  mov     [rbp+var_8], rdi
0x18024b66b  mul     [rbp+arg_18]
0x18024b66f  test    rdx, rdx
0x18024b672  jnz     loc_18024B81D
0x18024b678  mov     edx, eax; cbInit
0x18024b67a  mov     rcx, rsi; pInit
0x18024b67d  call    cs:__imp_SHCreateMemStream
0x18024b683  mov     rdi, rax
0x18024b686  test    rax, rax
0x18024b689  jnz     short loc_18024B695
0x18024b68b  mov     ebx, 8007000Eh
0x18024b690  jmp     loc_18024B822
0x18024b695  xor     r8d, r8d; pMalloc
0x18024b698  lea     rdx, [rbp+ppvObject]; ppvObject
0x18024b69c  lea     rcx, _GUID_7279fc81_709d_4095_b63d_69fe4b0d9030; riid
0x18024b6a3  call    cs:__imp_CreateXmlReader
0x18024b6a9  mov     ebx, eax
0x18024b6ab  test    eax, eax
0x18024b6ad  js      loc_18024B822
0x18024b6b3  mov     rcx, [rbp+ppvObject]
0x18024b6b7  xor     r8d, r8d
0x18024b6ba  mov     rax, [rcx]
0x18024b6bd  lea     edx, [r8+4]
0x18024b6c1  mov     rax, [rax+28h]
0x18024b6c5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18024b6ca  mov     ebx, eax
0x18024b6cc  test    eax, eax
0x18024b6ce  js      loc_18024B822
0x18024b6d4  lea     rax, [rbp+var_10]
0x18024b6d8  xor     r9d, r9d; fEncodingHint
0x18024b6db  mov     [rsp+50h+ppInput], rax; ppInput
0x18024b6e0  lea     r8, pwszEncodingName; "UTF-16"
0x18024b6e7  xor     edx, edx; pMalloc
0x18024b6e9  mov     [rsp+50h+pwszBaseUri], 0; pwszBaseUri
0x18024b6f2  mov     rcx, rdi; pInputStream
0x18024b6f5  call    cs:__imp_CreateXmlReaderInputWithEncodingName
0x18024b6fb  mov     ebx, eax
0x18024b6fd  test    eax, eax
0x18024b6ff  js      loc_18024B822
0x18024b705  mov     rcx, [rbp+ppvObject]
0x18024b709  mov     rdx, [rbp+var_10]
0x18024b70d  mov     rax, [rcx]
0x18024b710  mov     rax, [rax+18h]
0x18024b714  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18024b719  jmp     short loc_18024B77D
0x18024b71b  mov     rcx, [rbp+ppvObject]
0x18024b71f  lea     rdx, [rbp+arg_8]
0x18024b723  mov     rax, [rcx]
0x18024b726  mov     rax, [rax+30h]
0x18024b72a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18024b72f  mov     ebx, eax
0x18024b731  test    eax, eax
0x18024b733  jnz     loc_18024B814
0x18024b739  mov     ecx, [rbp+arg_8]
0x18024b73c  sub     ecx, 1
0x18024b73f  jz      loc_18024B7CA
0x18024b745  sub     ecx, 2
0x18024b748  jz      short loc_18024B788
0x18024b74a  cmp     ecx, 0Ch
0x18024b74d  jnz     short loc_18024B71B
0x18024b74f  mov     rcx, [rbp+ppvObject]
0x18024b753  lea     r8, [rbp+arg_0]
0x18024b757  lea     rdx, [rbp+var_18]
0x18024b75b  mov     rax, [rcx]
0x18024b75e  mov     rax, [rax+70h]
0x18024b762  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18024b767  mov     ebx, eax
0x18024b769  test    eax, eax
0x18024b76b  js      loc_18024B822
0x18024b771  mov     rdx, [rbp+var_18]; unsigned __int16 *
0x18024b775  mov     rcx, r14; this
0x18024b778  call    ?HandleEndElement@SyncMLResultCollection@@QEAAJPEBG@Z; SyncMLResultCollection::HandleEndElement(ushort const *)
0x18024b77d  mov     ebx, eax
0x18024b77f  test    eax, eax
0x18024b781  jns     short loc_18024B71B
0x18024b783  jmp     loc_18024B822
0x18024b788  mov     rcx, [rbp+ppvObject]
0x18024b78c  lea     r8, [rbp+arg_0]
0x18024b790  lea     rdx, [rbp+var_18]
0x18024b794  mov     rax, [rcx]
0x18024b797  mov     rax, [rax+80h]
0x18024b79e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18024b7a3  mov     ebx, eax
0x18024b7a5  test    eax, eax
0x18024b7a7  js      short loc_18024B822
0x18024b7a9  mov     rcx, [r14+30h]
0x18024b7ad  xor     ebx, ebx
0x18024b7af  test    rcx, rcx
0x18024b7b2  jz      short loc_18024B7C6
0x18024b7b4  mov     rax, [rcx]
0x18024b7b7  mov     rdx, [rbp+var_18]
0x18024b7bb  mov     rax, [rax+18h]
0x18024b7bf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18024b7c4  mov     ebx, eax
0x18024b7c6  test    ebx, ebx
0x18024b7c8  jmp     short loc_18024B781
0x18024b7ca  mov     rcx, [rbp+ppvObject]
0x18024b7ce  mov     rax, [rcx]
0x18024b7d1  mov     rax, [rax+0A0h]
0x18024b7d8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18024b7dd  test    eax, eax
0x18024b7df  jnz     loc_18024B71B
0x18024b7e5  mov     rcx, [rbp+ppvObject]
0x18024b7e9  lea     r8, [rbp+arg_0]
0x18024b7ed  lea     rdx, [rbp+var_18]
0x18024b7f1  mov     rax, [rcx]
0x18024b7f4  mov     rax, [rax+70h]
0x18024b7f8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18024b7fd  mov     ebx, eax
0x18024b7ff  test    eax, eax
0x18024b801  js      short loc_18024B822
0x18024b803  mov     rdx, [rbp+var_18]; unsigned __int16 *
0x18024b807  mov     rcx, r14; this
0x18024b80a  call    ?HandleStartElement@SyncMLResultCollection@@QEAAJPEBG@Z; SyncMLResultCollection::HandleStartElement(ushort const *)
0x18024b80f  jmp     loc_18024B77D
0x18024b814  cmp     eax, 1
0x18024b817  jnz     short loc_18024B822
0x18024b819  xor     ebx, ebx
0x18024b81b  jmp     short loc_18024B822
0x18024b81d  mov     ebx, 80070216h
0x18024b822  mov     eax, cs:dword_180380B68
0x18024b828  cmp     eax, 4
0x18024b82b  jbe     short loc_18024B859
0x18024b82d  lea     rax, aParse; "Parse"
0x18024b834  mov     dword ptr [rbp+arg_18], ebx
0x18024b837  mov     [rbp+var_8], rax
0x18024b83b  lea     rdx, byte_180370E35
0x18024b842  lea     rax, [rbp+arg_18]
0x18024b846  mov     [rsp+50h+ppInput], rax
0x18024b84b  lea     rax, [rbp+var_8]
0x18024b84f  mov     [rsp+50h+pwszBaseUri], rax
0x18024b854  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &)
0x18024b859  mov     rcx, [rbp+ppvObject]
0x18024b85d  test    rcx, rcx
0x18024b860  jz      short loc_18024B876
0x18024b862  mov     rax, [rcx]
0x18024b865  mov     rax, [rax+10h]
0x18024b869  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18024b86e  mov     [rbp+ppvObject], 0
0x18024b876  test    rdi, rdi
0x18024b879  jz      short loc_18024B88A
0x18024b87b  mov     rax, [rdi]
0x18024b87e  mov     rcx, rdi
0x18024b881  mov     rax, [rax+10h]
0x18024b885  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18024b88a  mov     rcx, [rbp+var_10]
0x18024b88e  test    rcx, rcx
0x18024b891  jz      short loc_18024B89F
0x18024b893  mov     rax, [rcx]
0x18024b896  mov     rax, [rax+10h]
0x18024b89a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18024b89f  mov     eax, ebx
0x18024b8a1  add     rsp, 50h
0x18024b8a5  pop     r14
0x18024b8a7  pop     rdi
0x18024b8a8  pop     rsi
0x18024b8a9  pop     rbx
0x18024b8aa  pop     rbp
0x18024b8ab  retn
```
