# AxiGetFullPathNameW(ushort const *,int,ushort * *,ushort const * *)

- ea: `0x4083bc`
- end: `0x40847a`
- name: `?AxiGetFullPathNameW@@YGJPBGHPAPAGPAPBG@Z`
- size: `190`
- prototype: `int __userpurge@<eax>(const WCHAR *@<ecx>, unsigned __int16 *, int, unsigned __int16 **, const unsigned __int16 **)`
- caller_count: `1`
- callee_count: `2`
- tags: `service_task`

## callers

- `0x408480`

## callees

- `0x4066c4`
- `0x4083bc`

## import_xrefs

- `KERNEL32!GetFullPathNameW` at `0x4083fb`
- `KERNEL32!GetFullPathNameW` at `0x408422`
- `KERNEL32!GetFullPathNameW` at `0x4083fb`
- `KERNEL32!GetFullPathNameW` at `0x408422`
- `msvcrt!wcschr` at `0x408445`
- `msvcrt!wcschr` at `0x408445`
- `ole32!CoTaskMemAlloc` at `0x40840b`
- `ole32!CoTaskMemAlloc` at `0x40840b`
- `ole32!CoTaskMemFree` at `0x40846b`
- `ole32!CoTaskMemFree` at `0x40846b`

## pseudocode

```c
int __userpurge AxiGetFullPathNameW@<eax>(
        const WCHAR *a1@<ecx>,
        unsigned __int16 *a2,
        int a3,
        unsigned __int16 **a4,
        const unsigned __int16 **a5)
{
  int ErrorError; // esi
  WCHAR *v6; // edi
  DWORD FullPathNameW; // eax
  DWORD v8; // eax
  wchar_t *v9; // eax
  int v10; // ecx
  DWORD nBufferLength; // [esp+10h] [ebp-Ch]
  LPWSTR FilePart; // [esp+14h] [ebp-8h] BYREF
  WCHAR Buffer; // [esp+18h] [ebp-4h] BYREF

  ErrorError = -2147024809;
  v6 = 0;
  if ( !a2 )
  {
    ErrorError = -2147467261;
    goto LABEL_15;
  }
  *(_DWORD *)a2 = 0;
  if ( a1 )
  {
    FilePart = 0;
    Buffer = 0;
    FullPathNameW = GetFullPathNameW(a1, 1u, &Buffer, 0);
    nBufferLength = FullPathNameW;
    if ( !FullPathNameW )
      goto LABEL_6;
    v6 = (WCHAR *)CoTaskMemAlloc(2 * FullPathNameW);
    if ( !v6 )
    {
      ErrorError = -2147024882;
      goto LABEL_15;
    }
    v8 = GetFullPathNameW(a1, nBufferLength, v6, &FilePart);
    if ( v8 )
    {
      if ( v8 < nBufferLength && FilePart )
      {
        v9 = _wcschr(FilePart, 0x2Eu);
        v10 = 0;
        if ( !v9 )
          v10 = -2147024809;
        ErrorError = v10;
        if ( v9 )
        {
          *(_DWORD *)a2 = v6;
          v6 = 0;
        }
      }
    }
    else
    {
LABEL_6:
      ErrorError = HRESULTFromLastErrorError();
    }
  }
LABEL_15:
  CoTaskMemFree(v6);
  return ErrorError;
}

```

## disassembly

```asm
0x4083bc  mov     edi, edi
0x4083be  push    ebp
0x4083bf  mov     ebp, esp
0x4083c1  sub     esp, 10h
0x4083c4  push    ebx
0x4083c5  mov     ebx, [ebp+arg_0]
0x4083c8  xor     edx, edx
0x4083ca  mov     eax, ecx
0x4083cc  mov     [ebp+lpFileName], eax
0x4083cf  push    esi
0x4083d0  mov     esi, 80070057h
0x4083d5  push    edi
0x4083d6  mov     edi, edx
0x4083d8  test    ebx, ebx
0x4083da  jz      loc_408465
0x4083e0  mov     [ebx], edx
0x4083e2  test    eax, eax
0x4083e4  jz      loc_40846A
0x4083ea  xor     ecx, ecx
0x4083ec  mov     [ebp+FilePart], edx
0x4083ef  push    edx; lpFilePart
0x4083f0  mov     [ebp+Buffer], cx
0x4083f4  lea     ecx, [ebp+Buffer]
0x4083f7  push    ecx; lpBuffer
0x4083f8  push    1; nBufferLength
0x4083fa  push    eax; lpFileName
0x4083fb  call    ds:__imp__GetFullPathNameW@16; GetFullPathNameW(x,x,x,x)
0x408401  mov     [ebp+nBufferLength], eax
0x408404  test    eax, eax
0x408406  jz      short loc_40842C
0x408408  add     eax, eax
0x40840a  push    eax; cb
0x40840b  call    ds:__imp__CoTaskMemAlloc@4; CoTaskMemAlloc(x)
0x408411  mov     edi, eax
0x408413  test    edi, edi
0x408415  jz      short loc_40845E
0x408417  lea     eax, [ebp+FilePart]
0x40841a  push    eax; lpFilePart
0x40841b  push    edi; lpBuffer
0x40841c  push    [ebp+nBufferLength]; nBufferLength
0x40841f  push    [ebp+lpFileName]; lpFileName
0x408422  call    ds:__imp__GetFullPathNameW@16; GetFullPathNameW(x,x,x,x)
0x408428  test    eax, eax
0x40842a  jnz     short loc_408435
0x40842c  call    ?HRESULTFromLastErrorError@@YGJXZ; HRESULTFromLastErrorError(void)
0x408431  mov     esi, eax
0x408433  jmp     short loc_40846A
0x408435  cmp     eax, [ebp+nBufferLength]
0x408438  jnb     short loc_40846A
0x40843a  cmp     [ebp+FilePart], 0
0x40843e  jz      short loc_40846A
0x408440  push    2Eh ; '.'; Ch
0x408442  push    [ebp+FilePart]; Str
0x408445  call    ds:__imp__wcschr
0x40844b  pop     ecx
0x40844c  pop     ecx
0x40844d  xor     ecx, ecx
0x40844f  test    eax, eax
0x408451  cmovz   ecx, esi
0x408454  mov     esi, ecx
0x408456  jz      short loc_40846A
0x408458  mov     [ebx], edi
0x40845a  xor     edi, edi
0x40845c  jmp     short loc_40846A
0x40845e  mov     esi, 8007000Eh
0x408463  jmp     short loc_40846A
0x408465  mov     esi, 80004003h
0x40846a  push    edi; pv
0x40846b  call    ds:__imp__CoTaskMemFree@4; CoTaskMemFree(x)
0x408471  pop     edi
0x408472  mov     eax, esi
0x408474  pop     esi
0x408475  pop     ebx
0x408476  leave
0x408477  retn    8
```
