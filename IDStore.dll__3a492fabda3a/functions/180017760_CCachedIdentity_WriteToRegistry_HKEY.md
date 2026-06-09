# CCachedIdentity::WriteToRegistry(HKEY__ *)

- ea: `0x180017760`
- end: `0x18001789d`
- name: `?WriteToRegistry@CCachedIdentity@@QEAAJPEAUHKEY__@@@Z`
- size: `317`
- prototype: `__int64 __fastcall(struct _GUID *this, HKEY)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1800178a4`

## callees

- `0x180009c30`
- `0x18000a680`
- `0x18000ada0`
- `0x180017700`
- `0x180017760`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180017863`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18001787c`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180017863`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18001787c`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180017871`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18001788a`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180017871`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18001788a`

## pseudocode

```c
__int64 __fastcall CCachedIdentity::WriteToRegistry(struct _GUID *this, HKEY a2)
{
  unsigned __int16 *v2; // rdi
  int v5; // ebx
  int v6; // eax
  void *v7; // rsi
  HANDLE ProcessHeap; // rax
  HANDLE v9; // rax
  unsigned __int16 *v11; // [rsp+20h] [rbp-40h] BYREF
  unsigned int v12[4]; // [rsp+28h] [rbp-38h]
  int v13; // [rsp+38h] [rbp-28h]
  LPVOID lpMem[3]; // [rsp+40h] [rbp-20h] BYREF
  int v15; // [rsp+58h] [rbp-8h]

  v2 = 0;
  v11 = 0;
  *(_QWORD *)v12 = 0;
  v13 = 0;
  lpMem[0] = 0;
  lpMem[1] = 0;
  v15 = 0;
  v5 = CDynamicString::Assign((CDynamicString *)lpMem, &byte_18001F5B0);
  if ( v5 >= 0 )
  {
    v5 = CDynamicString::RegWriteString((const BYTE **)&this[3], a2, L"DisplayName");
    if ( v5 >= 0 )
    {
      v5 = CDynamicString::RegWriteString((const BYTE **)&this[5], a2, L"UserName");
      if ( v5 >= 0 )
      {
        v6 = CDynamicArray<unsigned short>::Grow(&v11, 39);
        v2 = v11;
        if ( v6 )
        {
          v5 = IDGuidToString(this, v11, v12[1]);
          if ( v5 >= 0 )
          {
            v12[0] = 39;
            v5 = CDynamicString::RegWriteString((const BYTE **)&v11, a2, L"ProviderGUID");
            if ( v5 >= 0 )
            {
              v5 = CDynamicString::RegWriteString((const BYTE **)&this[1], a2, L"ProviderName");
              if ( v5 >= 0 )
                v5 = CDynamicString::RegWriteString((const BYTE **)lpMem, a2, L"SAMName");
            }
          }
        }
        else
        {
          v5 = -2147024882;
        }
      }
    }
  }
  v7 = lpMem[0];
  if ( lpMem[0] )
  {
    ProcessHeap = GetProcessHeap();
    HeapFree(ProcessHeap, 0, v7);
  }
  if ( v2 )
  {
    v9 = GetProcessHeap();
    HeapFree(v9, 0, v2);
  }
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x180017760  push    rbp
0x180017762  push    rbx
0x180017763  push    rsi
0x180017764  push    rdi
0x180017765  push    r14
0x180017767  mov     rbp, rsp
0x18001776a  sub     rsp, 60h
0x18001776e  xor     edi, edi
0x180017770  mov     rsi, rdx
0x180017773  mov     r14, rcx
0x180017776  mov     [rbp+var_40], rdi
0x18001777a  lea     rdx, byte_18001F5B0; unsigned __int16 *
0x180017781  mov     qword ptr [rbp+var_38], rdi
0x180017785  lea     rcx, [rbp+lpMem]; this
0x180017789  mov     [rbp+var_28], edi
0x18001778c  mov     [rbp+lpMem], rdi
0x180017790  mov     [rbp+var_18], rdi
0x180017794  mov     [rbp+var_8], edi
0x180017797  call    ?Assign@CDynamicString@@QEAAJPEBG@Z; CDynamicString::Assign(ushort const *)
0x18001779c  mov     ebx, eax
0x18001779e  test    eax, eax
0x1800177a0  js      loc_18001785A
0x1800177a6  lea     rcx, [r14+30h]; this
0x1800177aa  mov     rdx, rsi; HKEY
0x1800177ad  lea     r8, aDisplayname; "DisplayName"
0x1800177b4  call    ?RegWriteString@CDynamicString@@QEAAJPEAUHKEY__@@PEBG@Z; CDynamicString::RegWriteString(HKEY__ *,ushort const *)
0x1800177b9  mov     ebx, eax
0x1800177bb  test    eax, eax
0x1800177bd  js      loc_18001785A
0x1800177c3  lea     rcx, [r14+50h]; this
0x1800177c7  mov     rdx, rsi; HKEY
0x1800177ca  lea     r8, aUsername; "UserName"
0x1800177d1  call    ?RegWriteString@CDynamicString@@QEAAJPEAUHKEY__@@PEBG@Z; CDynamicString::RegWriteString(HKEY__ *,ushort const *)
0x1800177d6  mov     ebx, eax
0x1800177d8  test    eax, eax
0x1800177da  js      short loc_18001785A
0x1800177dc  lea     edx, [rdi+27h]
0x1800177df  lea     rcx, [rbp+var_40]
0x1800177e3  call    ?Grow@?$CDynamicArray@G@@QEAAHK@Z; CDynamicArray<ushort>::Grow(ulong)
0x1800177e8  mov     rdi, [rbp+var_40]
0x1800177ec  test    eax, eax
0x1800177ee  jnz     short loc_1800177F7
0x1800177f0  mov     ebx, 8007000Eh
0x1800177f5  jmp     short loc_18001785A
0x1800177f7  mov     r8d, [rbp+var_38+4]; unsigned int
0x1800177fb  mov     rdx, rdi; unsigned __int16 *
0x1800177fe  mov     rcx, r14; struct _GUID *
0x180017801  call    ?IDGuidToString@@YAJPEBU_GUID@@PEAGK@Z; IDGuidToString(_GUID const *,ushort *,ulong)
0x180017806  mov     ebx, eax
0x180017808  test    eax, eax
0x18001780a  js      short loc_18001785A
0x18001780c  mov     [rbp+var_38], 27h ; '''
0x180017813  lea     r8, aProviderguid; "ProviderGUID"
0x18001781a  mov     rdx, rsi; HKEY
0x18001781d  lea     rcx, [rbp+var_40]; this
0x180017821  call    ?RegWriteString@CDynamicString@@QEAAJPEAUHKEY__@@PEBG@Z; CDynamicString::RegWriteString(HKEY__ *,ushort const *)
0x180017826  mov     ebx, eax
0x180017828  test    eax, eax
0x18001782a  js      short loc_18001785A
0x18001782c  lea     rcx, [r14+10h]; this
0x180017830  mov     rdx, rsi; HKEY
0x180017833  lea     r8, aProvidername; "ProviderName"
0x18001783a  call    ?RegWriteString@CDynamicString@@QEAAJPEAUHKEY__@@PEBG@Z; CDynamicString::RegWriteString(HKEY__ *,ushort const *)
0x18001783f  mov     ebx, eax
0x180017841  test    eax, eax
0x180017843  js      short loc_18001785A
0x180017845  lea     r8, aSamname; "SAMName"
0x18001784c  mov     rdx, rsi; HKEY
0x18001784f  lea     rcx, [rbp+lpMem]; this
0x180017853  call    ?RegWriteString@CDynamicString@@QEAAJPEAUHKEY__@@PEBG@Z; CDynamicString::RegWriteString(HKEY__ *,ushort const *)
0x180017858  mov     ebx, eax
0x18001785a  mov     rsi, [rbp+lpMem]
0x18001785e  test    rsi, rsi
0x180017861  jz      short loc_180017877
0x180017863  call    cs:__imp_GetProcessHeap
0x180017869  mov     r8, rsi; lpMem
0x18001786c  xor     edx, edx; dwFlags
0x18001786e  mov     rcx, rax; hHeap
0x180017871  call    cs:__imp_HeapFree
0x180017877  test    rdi, rdi
0x18001787a  jz      short loc_180017890
0x18001787c  call    cs:__imp_GetProcessHeap
0x180017882  mov     r8, rdi; lpMem
0x180017885  xor     edx, edx; dwFlags
0x180017887  mov     rcx, rax; hHeap
0x18001788a  call    cs:__imp_HeapFree
0x180017890  mov     eax, ebx
0x180017892  add     rsp, 60h
0x180017896  pop     r14
0x180017898  pop     rdi
0x180017899  pop     rsi
0x18001789a  pop     rbx
0x18001789b  pop     rbp
0x18001789c  retn
```
