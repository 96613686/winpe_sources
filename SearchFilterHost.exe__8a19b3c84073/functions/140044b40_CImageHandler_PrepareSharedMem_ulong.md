# CImageHandler::PrepareSharedMem(ulong)

- ea: `0x140044b40`
- end: `0x140044bfd`
- name: `?PrepareSharedMem@CImageHandler@@QEAAJK@Z`
- size: `189`
- prototype: `int(CImageHandler *__hidden this, unsigned int)`
- caller_count: `1`
- callee_count: `4`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x1400459e0`

## callees

- `0x140009f14`
- `0x14001e440`
- `0x140044130`
- `0x140044b40`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140044bad`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140044bad`
- `api-ms-win-core-memory-l1-1-0!MapViewOfFile` at `0x140044ba3`
- `api-ms-win-core-memory-l1-1-0!MapViewOfFile` at `0x140044ba3`

## string_xrefs

- `0x140044bd8`: `onecoreuap\base\appmodel\Search\common\include\MemMappedImage.h`
- `0x140044b7a`: `onecoreuap\base\appmodel\search\common\imageembedding\ImageHandler.hxx`

## pseudocode

```c
__int64 __fastcall CImageHandler::PrepareSharedMem(
        CImageHandler *this,
        struct _SECURITY_ATTRIBUTES *a2,
        __int64 a3,
        __int64 a4)
{
  SIZE_T v5; // rsi
  unsigned int v6; // ebx
  int ImageMapping; // eax
  signed int LastError; // eax
  int dwNumberOfBytesToMap; // [rsp+20h] [rbp-18h]
  wil::details::in1diag3 *retaddr; // [rsp+38h] [rbp+0h]

  v5 = (unsigned int)a2;
  if ( !*((_QWORD *)this + 1) || (v6 = 0, *((_DWORD *)this + 4) < (unsigned int)a2) )
  {
    ImageMapping = CMemMappedImage::CreateImageMapping(this, a2, a3, a4, (DWORD)a2);
    v6 = ImageMapping;
    if ( ImageMapping >= 0 )
    {
      *((_QWORD *)this + 1) = MapViewOfFile(*(HANDLE *)this, 0xF001Fu, 0, 0, v5);
      LastError = GetLastError();
      v6 = LastError;
      if ( *((_QWORD *)this + 1) )
      {
        *((_DWORD *)this + 4) = v5;
        return 0;
      }
      else
      {
        if ( LastError > 0 )
          v6 = (unsigned __int16)LastError | 0x80070000;
        SearchIndexerTrace::Error(
          (wchar_t *)L"onecoreuap\\base\\appmodel\\Search\\common\\include\\MemMappedImage.h",
          (const wchar_t *)0x57,
          (unsigned int)L"CMemMappedImage::MapViewOfImage : MapViewOfFile failed with hr(0x%08x)",
          (const wchar_t *)v6);
      }
    }
    else
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x117,
        (unsigned int)"onecoreuap\\base\\appmodel\\search\\common\\imageembedding\\ImageHandler.hxx",
        (const char *)(unsigned int)ImageMapping,
        dwNumberOfBytesToMap);
    }
  }
  return v6;
}

```

## disassembly

```asm
0x140044b40  mov     [rsp+arg_0], rbx
0x140044b45  mov     [rsp+arg_8], rsi
0x140044b4a  push    rdi
0x140044b4b  sub     rsp, 30h
0x140044b4f  cmp     qword ptr [rcx+8], 0
0x140044b54  mov     rdi, rcx
0x140044b57  mov     esi, edx
0x140044b59  jz      short loc_140044B66
0x140044b5b  xor     ebx, ebx
0x140044b5d  cmp     [rcx+10h], esi
0x140044b60  jnb     loc_140044BEB
0x140044b66  mov     [rsp+38h+dwNumberOfBytesToMap], esi; int
0x140044b6a  call    ?CreateImageMapping@CMemMappedImage@@QEAAJQEAU_SECURITY_ATTRIBUTES@@KKKQEB_W@Z; CMemMappedImage::CreateImageMapping(_SECURITY_ATTRIBUTES * const,ulong,ulong,ulong,wchar_t const * const)
0x140044b6f  mov     ebx, eax
0x140044b71  test    eax, eax
0x140044b73  jns     short loc_140044B90
0x140044b75  mov     rcx, [rsp+38h]; this
0x140044b7a  lea     r8, aOnecoreuapBase_18; "onecoreuap\\base\\appmodel\\search\\com"...
0x140044b81  mov     r9d, eax; char *
0x140044b84  mov     edx, 117h; void *
0x140044b89  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140044b8e  jmp     short loc_140044BEB
0x140044b90  mov     rcx, [rdi]; hFileMappingObject
0x140044b93  xor     r9d, r9d; dwFileOffsetLow
0x140044b96  xor     r8d, r8d; dwFileOffsetHigh
0x140044b99  mov     qword ptr [rsp+38h+dwNumberOfBytesToMap], rsi; dwNumberOfBytesToMap
0x140044b9e  mov     edx, 0F001Fh; dwDesiredAccess
0x140044ba3  call    cs:__imp_MapViewOfFile
0x140044ba9  mov     [rdi+8], rax
0x140044bad  call    cs:__imp_GetLastError
0x140044bb3  cmp     qword ptr [rdi+8], 0
0x140044bb8  mov     ebx, eax
0x140044bba  jnz     short loc_140044BE6
0x140044bbc  test    eax, eax
0x140044bbe  jle     short loc_140044BC9
0x140044bc0  movzx   ebx, ax
0x140044bc3  or      ebx, 80070000h
0x140044bc9  mov     r9d, ebx; wchar_t *
0x140044bcc  lea     r8, aCmemmappedimag_0; "CMemMappedImage::MapViewOfImage : MapVi"...
0x140044bd3  mov     edx, 57h ; 'W'; wchar_t *
0x140044bd8  lea     rcx, aOnecoreuapBase_7; "onecoreuap\\base\\appmodel\\Search\\com"...
0x140044bdf  call    ?Error@SearchIndexerTrace@@YAXPEB_WI0ZZ; SearchIndexerTrace::Error(wchar_t const *,uint,wchar_t const *,...)
0x140044be4  jmp     short loc_140044BEB
0x140044be6  mov     [rdi+10h], esi
0x140044be9  xor     ebx, ebx
0x140044beb  mov     rsi, [rsp+38h+arg_8]
0x140044bf0  mov     eax, ebx
0x140044bf2  mov     rbx, [rsp+38h+arg_0]
0x140044bf7  add     rsp, 30h
0x140044bfb  pop     rdi
0x140044bfc  retn
```
