# SyncMLParser::Parse(ushort *,SyncMLResultCollection &)

- ea: `0x18024b0c4`
- end: `0x18024b387`
- name: `?Parse@SyncMLParser@@QEAAJPEAGAEAVSyncMLResultCollection@@@Z`
- size: `707`
- prototype: `int(SyncMLParser *__hidden this, unsigned __int16 *, struct SyncMLResultCollection *)`
- caller_count: `2`
- callee_count: `7`
- tags: `registry_config`

## callers

- `0x18023fe24`
- `0x18024bf6c`

## callees

- `0x180001310`
- `0x1802425ec`
- `0x180245e74`
- `0x1802461c4`
- `0x180246400`
- `0x18024b0c4`
- `0x18024f010`

## import_xrefs

- `SHLWAPI!__imp_SHCreateMemStream` at `0x18024b145`
- `SHLWAPI!__imp_SHCreateMemStream` at `0x18024b145`
- `XmlLite!CreateXmlReader` at `0x18024b171`
- `XmlLite!CreateXmlReader` at `0x18024b171`
- `XmlLite!CreateXmlReaderInputWithEncodingName` at `0x18024b1c9`
- `XmlLite!CreateXmlReaderInputWithEncodingName` at `0x18024b1c9`

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
0x18024b0c4  mov     [rsp-28h+arg_0], rcx
0x18024b0c9  push    rbp
0x18024b0ca  push    rbx
0x18024b0cb  push    rsi
0x18024b0cc  push    rdi
0x18024b0cd  push    r14
0x18024b0cf  mov     rbp, rsp
0x18024b0d2  sub     rsp, 50h
0x18024b0d6  xor     edi, edi
0x18024b0d8  mov     [rbp+ppvObject], 0
0x18024b0e0  mov     rcx, r8; this
0x18024b0e3  mov     [rbp+var_10], rdi
0x18024b0e7  mov     [rbp+arg_8], edi
0x18024b0ea  mov     r14, r8
0x18024b0ed  mov     [rbp+arg_18], rdi
0x18024b0f1  mov     rsi, rdx
0x18024b0f4  mov     [rbp+var_18], rdi
0x18024b0f8  mov     dword ptr [rbp+arg_0], edi
0x18024b0fb  call    ?Clear@SyncMLResultCollection@@QEAAXXZ; SyncMLResultCollection::Clear(void)
0x18024b100  test    rsi, rsi
0x18024b103  jnz     short loc_18024B10F
0x18024b105  mov     ebx, 80070057h
0x18024b10a  jmp     loc_18024B2FC
0x18024b10f  lea     r8, [rbp+arg_18]; unsigned __int64 *
0x18024b113  mov     edx, 7FFFFFFFh; unsigned __int64
0x18024b118  mov     rcx, rsi; unsigned __int16 *
0x18024b11b  call    ?StringCchLengthW@@YAJPEBG_KPEA_K@Z; StringCchLengthW(ushort const *,unsigned __int64,unsigned __int64 *)
0x18024b120  mov     ebx, eax
0x18024b122  test    eax, eax
0x18024b124  js      loc_18024B2FC
0x18024b12a  mov     eax, 2
0x18024b12f  mov     [rbp+var_8], rdi
0x18024b133  mul     [rbp+arg_18]
0x18024b137  test    rdx, rdx
0x18024b13a  jnz     loc_18024B2F7
0x18024b140  mov     edx, eax; cbInit
0x18024b142  mov     rcx, rsi; pInit
0x18024b145  call    cs:__imp_SHCreateMemStream
0x18024b14c  nop     dword ptr [rax+rax+00h]
0x18024b151  mov     rdi, rax
0x18024b154  test    rax, rax
0x18024b157  jnz     short loc_18024B163
0x18024b159  mov     ebx, 8007000Eh
0x18024b15e  jmp     loc_18024B2FC
0x18024b163  xor     r8d, r8d; pMalloc
0x18024b166  lea     rdx, [rbp+ppvObject]; ppvObject
0x18024b16a  lea     rcx, _GUID_7279fc81_709d_4095_b63d_69fe4b0d9030; riid
0x18024b171  call    cs:__imp_CreateXmlReader
0x18024b178  nop     dword ptr [rax+rax+00h]
0x18024b17d  mov     ebx, eax
0x18024b17f  test    eax, eax
0x18024b181  js      loc_18024B2FC
0x18024b187  mov     rcx, [rbp+ppvObject]
0x18024b18b  xor     r8d, r8d
0x18024b18e  mov     rax, [rcx]
0x18024b191  lea     edx, [r8+4]
0x18024b195  mov     rax, [rax+28h]
0x18024b199  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18024b19e  mov     ebx, eax
0x18024b1a0  test    eax, eax
0x18024b1a2  js      loc_18024B2FC
0x18024b1a8  lea     rax, [rbp+var_10]
0x18024b1ac  xor     r9d, r9d; fEncodingHint
0x18024b1af  mov     [rsp+50h+ppInput], rax; ppInput
0x18024b1b4  lea     r8, pwszEncodingName; "UTF-16"
0x18024b1bb  xor     edx, edx; pMalloc
0x18024b1bd  mov     [rsp+50h+pwszBaseUri], 0; pwszBaseUri
0x18024b1c6  mov     rcx, rdi; pInputStream
0x18024b1c9  call    cs:__imp_CreateXmlReaderInputWithEncodingName
0x18024b1d0  nop     dword ptr [rax+rax+00h]
0x18024b1d5  mov     ebx, eax
0x18024b1d7  test    eax, eax
0x18024b1d9  js      loc_18024B2FC
0x18024b1df  mov     rcx, [rbp+ppvObject]
0x18024b1e3  mov     rdx, [rbp+var_10]
0x18024b1e7  mov     rax, [rcx]
0x18024b1ea  mov     rax, [rax+18h]
0x18024b1ee  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18024b1f3  jmp     short loc_18024B257
0x18024b1f5  mov     rcx, [rbp+ppvObject]
0x18024b1f9  lea     rdx, [rbp+arg_8]
0x18024b1fd  mov     rax, [rcx]
0x18024b200  mov     rax, [rax+30h]
0x18024b204  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18024b209  mov     ebx, eax
0x18024b20b  test    eax, eax
0x18024b20d  jnz     loc_18024B2EE
0x18024b213  mov     ecx, [rbp+arg_8]
0x18024b216  sub     ecx, 1
0x18024b219  jz      loc_18024B2A4
0x18024b21f  sub     ecx, 2
0x18024b222  jz      short loc_18024B262
0x18024b224  cmp     ecx, 0Ch
0x18024b227  jnz     short loc_18024B1F5
0x18024b229  mov     rcx, [rbp+ppvObject]
0x18024b22d  lea     r8, [rbp+arg_0]
0x18024b231  lea     rdx, [rbp+var_18]
0x18024b235  mov     rax, [rcx]
0x18024b238  mov     rax, [rax+70h]
0x18024b23c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18024b241  mov     ebx, eax
0x18024b243  test    eax, eax
0x18024b245  js      loc_18024B2FC
0x18024b24b  mov     rdx, [rbp+var_18]; unsigned __int16 *
0x18024b24f  mov     rcx, r14; this
0x18024b252  call    ?HandleEndElement@SyncMLResultCollection@@QEAAJPEBG@Z; SyncMLResultCollection::HandleEndElement(ushort const *)
0x18024b257  mov     ebx, eax
0x18024b259  test    eax, eax
0x18024b25b  jns     short loc_18024B1F5
0x18024b25d  jmp     loc_18024B2FC
0x18024b262  mov     rcx, [rbp+ppvObject]
0x18024b266  lea     r8, [rbp+arg_0]
0x18024b26a  lea     rdx, [rbp+var_18]
0x18024b26e  mov     rax, [rcx]
0x18024b271  mov     rax, [rax+80h]
0x18024b278  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18024b27d  mov     ebx, eax
0x18024b27f  test    eax, eax
0x18024b281  js      short loc_18024B2FC
0x18024b283  mov     rcx, [r14+30h]
0x18024b287  xor     ebx, ebx
0x18024b289  test    rcx, rcx
0x18024b28c  jz      short loc_18024B2A0
0x18024b28e  mov     rax, [rcx]
0x18024b291  mov     rdx, [rbp+var_18]
0x18024b295  mov     rax, [rax+18h]
0x18024b299  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18024b29e  mov     ebx, eax
0x18024b2a0  test    ebx, ebx
0x18024b2a2  jmp     short loc_18024B25B
0x18024b2a4  mov     rcx, [rbp+ppvObject]
0x18024b2a8  mov     rax, [rcx]
0x18024b2ab  mov     rax, [rax+0A0h]
0x18024b2b2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18024b2b7  test    eax, eax
0x18024b2b9  jnz     loc_18024B1F5
0x18024b2bf  mov     rcx, [rbp+ppvObject]
0x18024b2c3  lea     r8, [rbp+arg_0]
0x18024b2c7  lea     rdx, [rbp+var_18]
0x18024b2cb  mov     rax, [rcx]
0x18024b2ce  mov     rax, [rax+70h]
0x18024b2d2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18024b2d7  mov     ebx, eax
0x18024b2d9  test    eax, eax
0x18024b2db  js      short loc_18024B2FC
0x18024b2dd  mov     rdx, [rbp+var_18]; unsigned __int16 *
0x18024b2e1  mov     rcx, r14; this
0x18024b2e4  call    ?HandleStartElement@SyncMLResultCollection@@QEAAJPEBG@Z; SyncMLResultCollection::HandleStartElement(ushort const *)
0x18024b2e9  jmp     loc_18024B257
0x18024b2ee  cmp     eax, 1
0x18024b2f1  jnz     short loc_18024B2FC
0x18024b2f3  xor     ebx, ebx
0x18024b2f5  jmp     short loc_18024B2FC
0x18024b2f7  mov     ebx, 80070216h
0x18024b2fc  mov     eax, cs:dword_180380B68
0x18024b302  cmp     eax, 4
0x18024b305  jbe     short loc_18024B333
0x18024b307  lea     rax, aParse; "Parse"
0x18024b30e  mov     dword ptr [rbp+arg_18], ebx
0x18024b311  mov     [rbp+var_8], rax
0x18024b315  lea     rdx, byte_180370E35
0x18024b31c  lea     rax, [rbp+arg_18]
0x18024b320  mov     [rsp+50h+ppInput], rax
0x18024b325  lea     rax, [rbp+var_8]
0x18024b329  mov     [rsp+50h+pwszBaseUri], rax
0x18024b32e  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &)
0x18024b333  mov     rcx, [rbp+ppvObject]
0x18024b337  test    rcx, rcx
0x18024b33a  jz      short loc_18024B350
0x18024b33c  mov     rax, [rcx]
0x18024b33f  mov     rax, [rax+10h]
0x18024b343  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18024b348  mov     [rbp+ppvObject], 0
0x18024b350  test    rdi, rdi
0x18024b353  jz      short loc_18024B364
0x18024b355  mov     rax, [rdi]
0x18024b358  mov     rcx, rdi
0x18024b35b  mov     rax, [rax+10h]
0x18024b35f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18024b364  mov     rcx, [rbp+var_10]
0x18024b368  test    rcx, rcx
0x18024b36b  jz      short loc_18024B379
0x18024b36d  mov     rax, [rcx]
0x18024b370  mov     rax, [rax+10h]
0x18024b374  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18024b379  mov     eax, ebx
0x18024b37b  add     rsp, 50h
0x18024b37f  pop     r14
0x18024b381  pop     rdi
0x18024b382  pop     rsi
0x18024b383  pop     rbx
0x18024b384  pop     rbp
0x18024b385  retn
```
