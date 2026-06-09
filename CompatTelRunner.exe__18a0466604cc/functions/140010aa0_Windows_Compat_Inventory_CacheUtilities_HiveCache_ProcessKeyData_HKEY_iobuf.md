# Windows::Compat::Inventory::CacheUtilities::HiveCache::ProcessKeyData(HKEY__ *,_iobuf *)

- ea: `0x140010aa0`
- end: `0x140010d68`
- name: `?ProcessKeyData@HiveCache@CacheUtilities@Inventory@Compat@Windows@@CAXPEAUHKEY__@@PEAU_iobuf@@@Z`
- size: `712`
- prototype: `void __fastcall(HKEY hkey, FILE *Stream)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1400108cc`

## callees

- `0x140001ba0`
- `0x1400026d8`
- `0x140010aa0`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140010b9e`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140010ca0`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140010b9e`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140010ca0`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x140010cae`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x140010cae`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x140010bac`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x140010bac`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x140010be2`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x140010be2`
- `api-ms-win-core-registry-l1-1-0!RegEnumValueW` at `0x140010b27`
- `api-ms-win-core-registry-l1-1-0!RegEnumValueW` at `0x140010b27`

## string_xrefs

- `0x140010b6b`: `		%ls	 unknown registry value type %d \n`
- `0x140010c30`: `Unknown registry value type: %d \n`

## pseudocode

```c
void __fastcall Windows::Compat::Inventory::CacheUtilities::HiveCache::ProcessKeyData(HKEY hkey, FILE *Stream)
{
  DWORD i; // esi
  unsigned int v5; // eax
  int *p_pvData; // rbx
  DWORD v7; // ebx
  HANDLE ProcessHeap; // rax
  unsigned int ValueW; // eax
  DWORD v10; // edx
  HANDLE v11; // rax
  const wchar_t *v12; // rdx
  DWORD cbData; // [rsp+40h] [rbp-C0h] BYREF
  DWORD Type; // [rsp+44h] [rbp-BCh] BYREF
  int v15; // [rsp+48h] [rbp-B8h] BYREF
  DWORD cchValueName; // [rsp+4Ch] [rbp-B4h] BYREF
  __int64 pvData; // [rsp+50h] [rbp-B0h] BYREF
  WCHAR ValueName[264]; // [rsp+60h] [rbp-A0h] BYREF

  i = 0;
  while ( 1 )
  {
    pvData = 0;
    v15 = 0;
    cbData = 0;
    Type = 0;
    ValueName[0] = 0;
    cchValueName = 260;
    v5 = RegEnumValueW(hkey, i, ValueName, &cchValueName, 0, &Type, 0, &cbData);
    if ( v5 == 259 )
      break;
    if ( v5 )
    {
      fwprintf(Stream, L"RegEnumValue failed: %d \n", v5);
      return;
    }
    ++i;
    switch ( Type )
    {
      case 1u:
      case 3u:
LABEL_12:
        v7 = cbData;
        ProcessHeap = GetProcessHeap();
        p_pvData = (int *)HeapAlloc(ProcessHeap, 0, v7);
        if ( !p_pvData )
        {
          fwprintf(Stream, L"HeapAlloc failed \n");
          return;
        }
        goto LABEL_13;
      case 4u:
        p_pvData = &v15;
        cbData = 4;
        goto LABEL_13;
      case 7u:
        goto LABEL_12;
      case 0xBu:
        p_pvData = (int *)&pvData;
        cbData = 8;
LABEL_13:
        ValueW = RegGetValueW(hkey, 0, ValueName, 0xFFFFu, 0, p_pvData, &cbData);
        if ( ValueW )
        {
          fwprintf(Stream, L"RegGetValue failed: %d \n", ValueW);
          return;
        }
        fwprintf(Stream, L"\t\t%-20ls\t", ValueName);
        switch ( Type )
        {
          case 1u:
LABEL_26:
            fwprintf(Stream, L"%ls \n", p_pvData);
            v11 = GetProcessHeap();
            HeapFree(v11, 0, p_pvData);
            break;
          case 3u:
            for ( i = 0; i < cbData; ++i )
            {
              v12 = L"%#0.2x";
              if ( i )
                v12 = L"%0.2x";
              fwprintf(Stream, v12, *((unsigned __int8 *)p_pvData + i));
            }
            fwprintf(Stream, L"\n");
            break;
          case 4u:
            fwprintf(Stream, L"%d \n");
            break;
          case 7u:
            v10 = cbData;
            i = 0;
            if ( (unsigned __int64)cbData >> 1 != 2 )
            {
              do
              {
                if ( !*((_WORD *)p_pvData + i) )
                {
                  *((_WORD *)p_pvData + i) = 32;
                  v10 = cbData;
                }
                ++i;
              }
              while ( i < ((unsigned __int64)v10 >> 1) - 2 );
            }
            goto LABEL_26;
          case 0xBu:
            fwprintf(Stream, L"%I64d \n", pvData);
            break;
          default:
            fwprintf(Stream, L"Unknown registry value type: %d \n");
            break;
        }
        break;
      default:
        fwprintf(Stream, L"\t\t%ls\t unknown registry value type %d \n", ValueName);
        break;
    }
  }
}

```

## disassembly

```asm
0x140010aa0  mov     [rsp-8+arg_10], rbx
0x140010aa5  push    rbp
0x140010aa6  push    rsi
0x140010aa7  push    rdi
0x140010aa8  push    r14
0x140010aaa  push    r15
0x140010aac  lea     rbp, [rsp-180h]
0x140010ab4  sub     rsp, 280h
0x140010abb  mov     rax, cs:__security_cookie
0x140010ac2  xor     rax, rsp
0x140010ac5  mov     [rbp+1A0h+var_30], rax
0x140010acc  xor     r15d, r15d
0x140010acf  mov     rdi, rdx
0x140010ad2  mov     esi, r15d
0x140010ad5  mov     r14, rcx
0x140010ad8  lea     rax, [rsp+2A0h+cbData]
0x140010add  mov     [rsp+2A0h+pvData], r15
0x140010ae2  mov     [rsp+2A0h+lpcbData], rax; lpcbData
0x140010ae7  lea     r9, [rsp+2A0h+cchValueName]; lpcchValueName
0x140010aec  lea     rax, [rsp+2A0h+Type]
0x140010af1  mov     [rsp+2A0h+lpData], r15; lpData
0x140010af6  mov     [rsp+2A0h+lpType], rax; lpType
0x140010afb  lea     r8, [rsp+2A0h+ValueName]; lpValueName
0x140010b00  mov     edx, esi; dwIndex
0x140010b02  mov     [rsp+2A0h+lpReserved], r15; lpReserved
0x140010b07  mov     rcx, r14; hKey
0x140010b0a  mov     [rsp+2A0h+var_258], r15d
0x140010b0f  mov     [rsp+2A0h+cbData], r15d
0x140010b14  mov     [rsp+2A0h+Type], r15d
0x140010b19  mov     [rsp+2A0h+ValueName], r15w
0x140010b1f  mov     [rsp+2A0h+cchValueName], 104h
0x140010b27  call    cs:__imp_RegEnumValueW
0x140010b2d  cmp     eax, 103h
0x140010b32  jz      loc_140010D42
0x140010b38  test    eax, eax
0x140010b3a  jnz     loc_140010D30
0x140010b40  mov     r9d, [rsp+2A0h+Type]
0x140010b45  inc     esi
0x140010b47  mov     eax, r9d
0x140010b4a  sub     eax, 1
0x140010b4d  jz      short loc_140010B9A
0x140010b4f  sub     eax, 2
0x140010b52  jz      short loc_140010B9A
0x140010b54  sub     eax, 1
0x140010b57  jz      short loc_140010B8B
0x140010b59  sub     eax, 3
0x140010b5c  jz      short loc_140010B9A
0x140010b5e  cmp     eax, 4
0x140010b61  jz      short loc_140010B7C
0x140010b63  lea     r8, [rsp+2A0h+ValueName]
0x140010b68  mov     rcx, rdi; Stream
0x140010b6b  lea     rdx, aLsUnknownRegis; "\t\t%ls\t unknown registry value type %"...
0x140010b72  call    fwprintf
0x140010b77  jmp     loc_140010AD8
0x140010b7c  lea     rbx, [rsp+2A0h+pvData]
0x140010b81  mov     [rsp+2A0h+cbData], 8
0x140010b89  jmp     short loc_140010BBE
0x140010b8b  lea     rbx, [rsp+2A0h+var_258]
0x140010b90  mov     [rsp+2A0h+cbData], 4
0x140010b98  jmp     short loc_140010BBE
0x140010b9a  mov     ebx, [rsp+2A0h+cbData]
0x140010b9e  call    cs:__imp_GetProcessHeap
0x140010ba4  mov     r8d, ebx; dwBytes
0x140010ba7  xor     edx, edx; dwFlags
0x140010ba9  mov     rcx, rax; hHeap
0x140010bac  call    cs:__imp_HeapAlloc
0x140010bb2  mov     rbx, rax
0x140010bb5  test    rax, rax
0x140010bb8  jz      loc_140010D1F
0x140010bbe  lea     rax, [rsp+2A0h+cbData]
0x140010bc3  mov     r9d, 0FFFFh; dwFlags
0x140010bc9  mov     [rsp+2A0h+lpData], rax; pcbData
0x140010bce  lea     r8, [rsp+2A0h+ValueName]; lpValue
0x140010bd3  mov     [rsp+2A0h+lpType], rbx; pvData
0x140010bd8  xor     edx, edx; lpSubKey
0x140010bda  mov     rcx, r14; hkey
0x140010bdd  mov     [rsp+2A0h+lpReserved], r15; pdwType
0x140010be2  call    cs:__imp_RegGetValueW
0x140010be8  mov     rcx, rdi; Stream
0x140010beb  test    eax, eax
0x140010bed  jnz     loc_140010D16
0x140010bf3  lea     r8, [rsp+2A0h+ValueName]
0x140010bf8  lea     rdx, a20ls_0; "\t\t%-20ls\t"
0x140010bff  call    fwprintf
0x140010c04  mov     r8d, [rsp+2A0h+Type]
0x140010c09  mov     eax, r8d
0x140010c0c  sub     eax, 1
0x140010c0f  jz      short loc_140010C8E
0x140010c11  sub     eax, 2
0x140010c14  jz      loc_140010CCD
0x140010c1a  sub     eax, 1
0x140010c1d  jz      loc_140010CB9
0x140010c23  sub     eax, 3
0x140010c26  jz      short loc_140010C57
0x140010c28  mov     rcx, rdi; Stream
0x140010c2b  cmp     eax, 4
0x140010c2e  jz      short loc_140010C41
0x140010c30  lea     rdx, aUnknownRegistr; "Unknown registry value type: %d \n"
0x140010c37  call    fwprintf
0x140010c3c  jmp     loc_140010AD8
0x140010c41  mov     r8, [rsp+2A0h+pvData]
0x140010c46  lea     rdx, aI64d; "%I64d \n"
0x140010c4d  call    fwprintf
0x140010c52  jmp     loc_140010AD8
0x140010c57  mov     edx, [rsp+2A0h+cbData]
0x140010c5b  mov     esi, r15d
0x140010c5e  mov     eax, edx
0x140010c60  shr     rax, 1
0x140010c63  cmp     rax, 2
0x140010c67  jz      short loc_140010C8E
0x140010c69  mov     ecx, esi
0x140010c6b  cmp     r15w, [rbx+rcx*2]
0x140010c70  jnz     short loc_140010C7C
0x140010c72  mov     word ptr [rbx+rcx*2], 20h ; ' '
0x140010c78  mov     edx, [rsp+2A0h+cbData]
0x140010c7c  inc     esi
0x140010c7e  mov     ecx, edx
0x140010c80  shr     rcx, 1
0x140010c83  sub     rcx, 2
0x140010c87  mov     eax, esi
0x140010c89  cmp     rax, rcx
0x140010c8c  jb      short loc_140010C69
0x140010c8e  mov     r8, rbx
0x140010c91  lea     rdx, aLs_1; "%ls \n"
0x140010c98  mov     rcx, rdi; Stream
0x140010c9b  call    fwprintf
0x140010ca0  call    cs:__imp_GetProcessHeap
0x140010ca6  mov     r8, rbx; lpMem
0x140010ca9  xor     edx, edx; dwFlags
0x140010cab  mov     rcx, rax; hHeap
0x140010cae  call    cs:__imp_HeapFree
0x140010cb4  jmp     loc_140010AD8
0x140010cb9  mov     r8d, [rsp+2A0h+var_258]
0x140010cbe  lea     rdx, aD_1; "%d \n"
0x140010cc5  mov     rcx, rdi
0x140010cc8  jmp     loc_140010C37
0x140010ccd  mov     esi, r15d
0x140010cd0  cmp     [rsp+2A0h+cbData], r15d
0x140010cd5  jbe     short loc_140010D02
0x140010cd7  mov     eax, esi
0x140010cd9  lea     rdx, a02x_1; "%#0.2x"
0x140010ce0  test    esi, esi
0x140010ce2  mov     rcx, rdi; Stream
0x140010ce5  movzx   r8d, byte ptr [rax+rbx]
0x140010cea  lea     rax, a02x; "%0.2x"
0x140010cf1  cmovnz  rdx, rax; Format
0x140010cf5  call    fwprintf
0x140010cfa  inc     esi
0x140010cfc  cmp     esi, [rsp+2A0h+cbData]
0x140010d00  jb      short loc_140010CD7
0x140010d02  lea     rdx, asc_1400ACFA0; "\n"
0x140010d09  mov     rcx, rdi; Stream
0x140010d0c  call    fwprintf
0x140010d11  jmp     loc_140010AD8
0x140010d16  lea     rdx, aReggetvalueFai; "RegGetValue failed: %d \n"
0x140010d1d  jmp     short loc_140010D3A
0x140010d1f  lea     rdx, aHeapallocFaile; "HeapAlloc failed \n"
0x140010d26  mov     rcx, rdi; Stream
0x140010d29  call    fwprintf
0x140010d2e  jmp     short loc_140010D42
0x140010d30  lea     rdx, aRegenumvalueFa; "RegEnumValue failed: %d \n"
0x140010d37  mov     rcx, rdi; Stream
0x140010d3a  mov     r8d, eax
0x140010d3d  call    fwprintf
0x140010d42  mov     rcx, [rbp+1A0h+var_30]
0x140010d49  xor     rcx, rsp; StackCookie
0x140010d4c  call    __security_check_cookie
0x140010d51  mov     rbx, [rsp+2A0h+arg_10]
0x140010d59  add     rsp, 280h
0x140010d60  pop     r15
0x140010d62  pop     r14
0x140010d64  pop     rdi
0x140010d65  pop     rsi
0x140010d66  pop     rbp
0x140010d67  retn
```
