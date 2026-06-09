# WaasMedic::XmlReader::Initialize(ushort const *)

- ea: `0x180036558`
- end: `0x1800366fb`
- name: `?Initialize@XmlReader@WaasMedic@@QEAAJPEBG@Z`
- size: `419`
- prototype: `int(WaasMedic::XmlReader *__hidden this, const unsigned __int16 *)`
- caller_count: `2`
- callee_count: `3`
- tags: `registry_config, installer_update`

## callers

- `0x180034290`
- `0x1800344c4`

## callees

- `0x18002543c`
- `0x180036558`
- `0x180064010`

## import_xrefs

- `api-ms-win-shcore-stream-l1-1-0!SHCreateStreamOnFileW` at `0x1800365a5`
- `api-ms-win-shcore-stream-l1-1-0!SHCreateStreamOnFileW` at `0x1800365a5`
- `XmlLite!CreateXmlReader` at `0x1800365f6`
- `XmlLite!CreateXmlReader` at `0x1800365f6`

## string_xrefs

- `0x1800365b1`: `Error creating file reader. hr=0x%08x`
- `0x18003662a`: `Error setting XmlReaderProperty_ConformanceLevel. hr=0x%08x`
- `0x180036602`: `Error creating xml reader. hr=0x%08x`
- `0x180036678`: `Error setting input for reader. hr=0x%08x`
- `0x180036652`: `Error setting XmlReaderProperty_DtdProcessing. hr=0x%08x`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall WaasMedic::XmlReader::Initialize(WaasMedic::XmlReader *this, const unsigned __int16 *a2)
{
  unsigned int v3; // edi
  HRESULT v4; // eax
  void *v5; // rcx
  HRESULT v6; // eax
  int v7; // eax
  int v8; // eax
  int v9; // eax
  void *v10; // rbx
  void *v11; // rcx
  void *v12; // rcx
  void *ppvObject; // [rsp+48h] [rbp+28h] BYREF
  IStream *ppstm; // [rsp+50h] [rbp+30h] BYREF

  ppstm = 0;
  ppvObject = 0;
  if ( a2 )
  {
    if ( *((_BYTE *)this + 12) )
    {
      v3 = -2147023649;
    }
    else
    {
      v4 = SHCreateStreamOnFileW(a2, 0, &ppstm);
      v3 = v4;
      if ( v4 >= 0 )
      {
        v5 = ppvObject;
        if ( ppvObject )
        {
          ppvObject = 0;
          (*(void (__fastcall **)(void *))(*(_QWORD *)v5 + 16LL))(v5);
        }
        v6 = CreateXmlReader(&GUID_7279fc81_709d_4095_b63d_69fe4b0d9030, &ppvObject, 0);
        v3 = v6;
        if ( v6 >= 0 )
        {
          v7 = (*(__int64 (__fastcall **)(void *, __int64, __int64))(*(_QWORD *)ppvObject + 40LL))(ppvObject, 1, 2);
          v3 = v7;
          if ( v7 >= 0 )
          {
            v8 = (*(__int64 (__fastcall **)(void *, __int64, __int64))(*(_QWORD *)ppvObject + 40LL))(ppvObject, 4, 1);
            v3 = v8;
            if ( v8 >= 0 )
            {
              v9 = (*(__int64 (__fastcall **)(void *, IStream *))(*(_QWORD *)ppvObject + 24LL))(ppvObject, ppstm);
              v3 = v9;
              if ( v9 >= 0 )
              {
                (*(void (__fastcall **)(IStream *))(*(_QWORD *)ppstm + 16LL))(ppstm);
                v10 = ppvObject;
                if ( *(void **)this != ppvObject )
                {
                  if ( ppvObject )
                    (*(void (__fastcall **)(void *))(*(_QWORD *)ppvObject + 8LL))(ppvObject);
                  v11 = *(void **)this;
                  *(_QWORD *)this = v10;
                  if ( v11 )
                    (*(void (__fastcall **)(void *))(*(_QWORD *)v11 + 16LL))(v11);
                }
                *((_BYTE *)this + 12) = 1;
              }
              else
              {
                LogLevelW(2u, L"Error setting input for reader. hr=0x%08x", (unsigned int)v9);
              }
            }
            else
            {
              LogLevelW(2u, L"Error setting XmlReaderProperty_DtdProcessing. hr=0x%08x", (unsigned int)v8);
            }
          }
          else
          {
            LogLevelW(2u, L"Error setting XmlReaderProperty_ConformanceLevel. hr=0x%08x", (unsigned int)v7);
          }
        }
        else
        {
          LogLevelW(2u, L"Error creating xml reader. hr=0x%08x", (unsigned int)v6);
        }
      }
      else
      {
        LogLevelW(2u, L"Error creating file reader. hr=0x%08x", (unsigned int)v4);
      }
    }
  }
  else
  {
    v3 = -2147024809;
  }
  v12 = ppvObject;
  if ( ppvObject )
  {
    ppvObject = 0;
    (*(void (__fastcall **)(void *))(*(_QWORD *)v12 + 16LL))(v12);
  }
  return v3;
}

```

## disassembly

```asm
0x180036558  mov     [rsp-18h+arg_0], rbx
0x18003655d  push    rbp
0x18003655e  push    rsi
0x18003655f  push    rdi
0x180036560  mov     rbp, rsp
0x180036563  sub     rsp, 20h
0x180036567  mov     rax, rdx
0x18003656a  mov     rsi, rcx
0x18003656d  mov     [rbp+ppstm], 0
0x180036575  mov     [rbp+ppvObject], 0
0x18003657d  test    rdx, rdx
0x180036580  jnz     short loc_18003658C
0x180036582  mov     edi, 80070057h
0x180036587  jmp     loc_1800366CE
0x18003658c  cmp     byte ptr [rcx+0Ch], 0
0x180036590  jz      short loc_18003659C
0x180036592  mov     edi, 800704DFh
0x180036597  jmp     loc_1800366CE
0x18003659c  lea     r8, [rbp+ppstm]; ppstm
0x1800365a0  xor     edx, edx; grfMode
0x1800365a2  mov     rcx, rax; pszFile
0x1800365a5  call    cs:__imp_SHCreateStreamOnFileW
0x1800365ab  mov     edi, eax
0x1800365ad  test    eax, eax
0x1800365af  jns     short loc_1800365CA
0x1800365b1  lea     rdx, aErrorCreatingF; "Error creating file reader. hr=0x%08x"
0x1800365b8  mov     r8d, eax
0x1800365bb  mov     ecx, 2; unsigned __int8
0x1800365c0  call    ?LogLevelW@@YAXEPEBGZZ; LogLevelW(uchar,ushort const *,...)
0x1800365c5  jmp     loc_1800366CE
0x1800365ca  mov     rcx, [rbp+ppvObject]
0x1800365ce  test    rcx, rcx
0x1800365d1  jz      short loc_1800365E8
0x1800365d3  mov     [rbp+ppvObject], 0
0x1800365db  mov     rax, [rcx]
0x1800365de  mov     rax, [rax+10h]
0x1800365e2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800365e7  nop
0x1800365e8  xor     r8d, r8d; pMalloc
0x1800365eb  lea     rdx, [rbp+ppvObject]; ppvObject
0x1800365ef  lea     rcx, _GUID_7279fc81_709d_4095_b63d_69fe4b0d9030; riid
0x1800365f6  call    cs:__imp_CreateXmlReader
0x1800365fc  mov     edi, eax
0x1800365fe  test    eax, eax
0x180036600  jns     short loc_18003660B
0x180036602  lea     rdx, aErrorCreatingX; "Error creating xml reader. hr=0x%08x"
0x180036609  jmp     short loc_1800365B8
0x18003660b  mov     rcx, [rbp+ppvObject]
0x18003660f  mov     rax, [rcx]
0x180036612  mov     edx, 1
0x180036617  lea     r8d, [rdx+1]
0x18003661b  mov     rax, [rax+28h]
0x18003661f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180036624  mov     edi, eax
0x180036626  test    eax, eax
0x180036628  jns     short loc_180036633
0x18003662a  lea     rdx, aErrorSettingXm; "Error setting XmlReaderProperty_Conform"...
0x180036631  jmp     short loc_1800365B8
0x180036633  mov     rcx, [rbp+ppvObject]
0x180036637  mov     rax, [rcx]
0x18003663a  mov     edx, 4
0x18003663f  lea     r8d, [rdx-3]
0x180036643  mov     rax, [rax+28h]
0x180036647  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003664c  mov     edi, eax
0x18003664e  test    eax, eax
0x180036650  jns     short loc_18003665E
0x180036652  lea     rdx, aErrorSettingXm_0; "Error setting XmlReaderProperty_DtdProc"...
0x180036659  jmp     loc_1800365B8
0x18003665e  mov     rcx, [rbp+ppvObject]
0x180036662  mov     rax, [rcx]
0x180036665  mov     rdx, [rbp+ppstm]
0x180036669  mov     rax, [rax+18h]
0x18003666d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180036672  mov     edi, eax
0x180036674  test    eax, eax
0x180036676  jns     short loc_180036684
0x180036678  lea     rdx, aErrorSettingIn; "Error setting input for reader. hr=0x%0"...
0x18003667f  jmp     loc_1800365B8
0x180036684  mov     rcx, [rbp+ppstm]
0x180036688  mov     rax, [rcx]
0x18003668b  mov     rax, [rax+10h]
0x18003668f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180036694  mov     rbx, [rbp+ppvObject]
0x180036698  cmp     [rsi], rbx
0x18003669b  jz      short loc_1800366CA
0x18003669d  test    rbx, rbx
0x1800366a0  jz      short loc_1800366B2
0x1800366a2  mov     rax, [rbx]
0x1800366a5  mov     rcx, rbx
0x1800366a8  mov     rax, [rax+8]
0x1800366ac  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800366b1  nop
0x1800366b2  mov     rcx, [rsi]
0x1800366b5  mov     [rsi], rbx
0x1800366b8  test    rcx, rcx
0x1800366bb  jz      short loc_1800366CA
0x1800366bd  mov     rax, [rcx]
0x1800366c0  mov     rax, [rax+10h]
0x1800366c4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800366c9  nop
0x1800366ca  mov     byte ptr [rsi+0Ch], 1
0x1800366ce  mov     rcx, [rbp+ppvObject]
0x1800366d2  test    rcx, rcx
0x1800366d5  jz      short loc_1800366EC
0x1800366d7  mov     [rbp+ppvObject], 0
0x1800366df  mov     rax, [rcx]
0x1800366e2  mov     rax, [rax+10h]
0x1800366e6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800366eb  nop
0x1800366ec  mov     eax, edi
0x1800366ee  mov     rbx, [rsp+20h+arg_0]
0x1800366f3  add     rsp, 20h
0x1800366f7  pop     rdi
0x1800366f8  pop     rsi
0x1800366f9  pop     rbp
0x1800366fa  retn
```
