# BiEnumerateElements

- ea: `0x140019bb8`
- end: `0x14001a25c`
- name: `BiEnumerateElements`
- size: `1700`
- prototype: `__int64 __fastcall(int, __int64, int, int, __int64, unsigned int *, _DWORD *, __int64, int)`
- caller_count: `2`
- callee_count: `10`
- tags: `registry_config, loader_planting`

## callers

- `0x1400186fc`
- `0x14001a264`

## callees

- `0x1400133e4`
- `0x140019544`
- `0x140019bb8`
- `0x14001a264`
- `0x14001a454`
- `0x14001e5e4`
- `0x14001ee20`
- `0x14001f324`
- `0x14001f980`
- `0x1400265e2`

## import_xrefs

- `msvcrt!wcstoul` at `0x140019ce7`
- `msvcrt!wcstoul` at `0x140019ce7`
- `ntdll!RtlAllocateHeap` at `0x140019df8`
- `ntdll!RtlAllocateHeap` at `0x140019fc2`
- `ntdll!RtlAllocateHeap` at `0x140019df8`
- `ntdll!RtlAllocateHeap` at `0x140019fc2`
- `ntdll!RtlFreeHeap` at `0x140019de0`
- `ntdll!RtlFreeHeap` at `0x14001a002`
- `ntdll!RtlFreeHeap` at `0x14001a01b`
- `ntdll!RtlFreeHeap` at `0x14001a197`
- `ntdll!RtlFreeHeap` at `0x14001a1b4`
- `ntdll!RtlFreeHeap` at `0x14001a1d8`
- `ntdll!RtlFreeHeap` at `0x14001a237`
- `ntdll!RtlFreeHeap` at `0x140019de0`
- `ntdll!RtlFreeHeap` at `0x14001a002`
- `ntdll!RtlFreeHeap` at `0x14001a01b`
- `ntdll!RtlFreeHeap` at `0x14001a197`
- `ntdll!RtlFreeHeap` at `0x14001a1b4`
- `ntdll!RtlFreeHeap` at `0x14001a1d8`
- `ntdll!RtlFreeHeap` at `0x14001a237`

## string_xrefs

- `0x14001a139`: `Failed to get registry value. Element: %ws Status: %x`
- `0x14001a119`: `Failed to convert registry data to element. Element: %ws, Status: %x`

## pseudocode

```c
__int64 __fastcall BiEnumerateElements(
        int a1,
        __int64 a2,
        int a3,
        int a4,
        __int64 a5,
        unsigned int *a6,
        _DWORD *a7,
        __int64 a8,
        int a9)
{
  unsigned int v10; // esi
  void *v11; // r14
  unsigned int *v12; // rbx
  int v13; // edi
  int v14; // eax
  unsigned int v15; // eax
  __int64 v16; // r13
  _QWORD *v17; // r12
  __int64 v18; // r14
  __int64 v19; // r15
  unsigned int v20; // r14d
  int v21; // r12d
  __int64 v22; // r9
  int RegistryValue; // eax
  unsigned int *v24; // r15
  GUID *Heap; // r14
  unsigned int v26; // edi
  int v27; // eax
  unsigned int v28; // eax
  size_t v29; // r15
  unsigned int v30; // edi
  unsigned int v31; // edi
  unsigned int v32; // eax
  unsigned int v33; // ecx
  int v34; // eax
  unsigned int v35; // r15d
  _QWORD *v36; // rdx
  PVOID v37; // rax
  PVOID v38; // r12
  unsigned int v40; // [rsp+58h] [rbp-69h]
  unsigned int Size; // [rsp+5Ch] [rbp-65h] BYREF
  unsigned int Size_4; // [rsp+60h] [rbp-61h]
  int v43; // [rsp+64h] [rbp-5Dh] BYREF
  _QWORD *v44; // [rsp+68h] [rbp-59h] BYREF
  unsigned int v45; // [rsp+70h] [rbp-51h] BYREF
  __int64 v46; // [rsp+78h] [rbp-49h] BYREF
  HANDLE Handle; // [rsp+80h] [rbp-41h] BYREF
  unsigned int v48; // [rsp+88h] [rbp-39h] BYREF
  unsigned int v49; // [rsp+8Ch] [rbp-35h]
  unsigned int v50; // [rsp+90h] [rbp-31h]
  PVOID P; // [rsp+98h] [rbp-29h] BYREF
  _QWORD *v52; // [rsp+A0h] [rbp-21h]
  HANDLE v53; // [rsp+A8h] [rbp-19h] BYREF
  PVOID v54; // [rsp+B0h] [rbp-11h]
  __int64 v55; // [rsp+B8h] [rbp-9h]

  v10 = 0;
  v53 = 0;
  v11 = 0;
  v48 = 0;
  v43 = 0;
  *a7 = 0;
  v45 = 0;
  Handle = 0;
  P = 0;
  v44 = 0;
  if ( a9 <= 0 )
  {
    v12 = a6;
    v13 = -1073741811;
    goto LABEL_93;
  }
  v13 = BiOpenKey(a2, L"Elements", 131097, &v53);
  if ( v13 >= 0 )
  {
    v14 = BiEnumerateSubKeys(v53, &v44, &v45);
    v13 = v14;
    if ( v14 < 0 )
    {
      BiLogMessage(4, L"Failed to enumerate subkeys. Status: %x", (unsigned int)v14);
      goto LABEL_86;
    }
    v15 = 0;
    v16 = a5;
    v46 = a5;
    v49 = 0;
    v52 = 0;
    v54 = 0;
    v40 = 0;
    v50 = 0;
    if ( v45 )
    {
      v17 = v44;
      while ( 1 )
      {
        v18 = v15;
        v19 = v17[v15];
        v55 = v19;
        v13 = BiOpenKey(v53, v19, 131097, &Handle);
        if ( v13 < 0 )
        {
          v13 = 0;
          goto LABEL_59;
        }
        v20 = wcstoul((const wchar_t *)v17[v18], 0, 16);
        Size_4 = v20;
        if ( v20 - 1 > 0xFFFFFFFD )
        {
          BiCloseKey(Handle);
          Handle = 0;
          goto LABEL_59;
        }
        v21 = HIBYTE(v20) & 0xF;
        if ( v21 == 1 )
          break;
        if ( (HIBYTE(v20) & 0xF) == 2 || (HIBYTE(v20) & 0xF) == 3 )
        {
          v22 = 1;
        }
        else
        {
          if ( (HIBYTE(v20) & 0xF) != 4 )
            break;
          v22 = 7;
        }
LABEL_16:
        RegistryValue = BiGetRegistryValue(Handle, L"Element", 0, v22, &P, &v48);
        v13 = RegistryValue;
        if ( RegistryValue != -1073741772 && RegistryValue != -1073741275 )
        {
          if ( RegistryValue != -1073741788 || v20 != 335544326 )
          {
            if ( RegistryValue < 0 )
            {
              BiLogMessage(
                4,
                L"Failed to get registry value. Element: %ws Status: %x",
                v19,
                (unsigned int)RegistryValue);
              Heap = 0;
              goto LABEL_71;
            }
            v24 = (unsigned int *)P;
            Heap = 0;
            v26 = 512;
            if ( v21 != 1 )
              v26 = 256;
            for ( Size = v26; ; v26 = Size )
            {
              if ( Heap )
                RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, Heap);
              Heap = (GUID *)RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 0, v26);
              if ( !Heap )
              {
                v13 = -1073741670;
                goto LABEL_71;
              }
              v27 = BiConvertRegistryDataToElement(a2, v24, v48, Size_4, a4, Heap, &Size);
              v13 = v27;
              if ( v27 != -1073741789 )
                break;
            }
            if ( v27 < 0 )
            {
              BiLogMessage(
                4,
                L"Failed to convert registry data to element. Element: %ws, Status: %x",
                v55,
                (unsigned int)v27);
              goto LABEL_71;
            }
            v28 = v10 + 24;
            if ( v10 + 24 >= v10 )
            {
              v29 = Size;
              v10 = v28 + Size;
              if ( v28 + Size >= v28 )
              {
                ++*a7;
                v30 = *a6;
                if ( *a6 >= v10 )
                {
                  *(_QWORD *)v16 = a5 + v10;
                  v32 = Size_4;
                  *(_DWORD *)(v16 + 8) = a3;
                  *(_DWORD *)(v16 + 12) = 1;
                  *(_DWORD *)(v16 + 16) = v32;
                  *(_DWORD *)(v16 + 20) = v29;
                  memcpy_0((void *)(v16 + 24), Heap, v29);
                  v52 = (_QWORD *)v16;
                  v31 = v30 - v10;
                  v16 = *(_QWORD *)v16;
                  v46 = v16;
                }
                else
                {
                  v31 = 0;
                }
                v40 = v31;
                if ( (a4 & 8) == 0 || v21 != 1 )
                {
                  v13 = 0;
                  if ( (a4 & 4) != 0 && Size_4 == 335544326 )
                  {
                    v37 = RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 0, v29);
                    v54 = v37;
                    if ( !v37 )
                    {
                      v13 = -1073741670;
                      goto LABEL_79;
                    }
                    memcpy_0(v37, Heap, v29);
                    v50 = (unsigned int)v29 >> 4;
                  }
                  goto LABEL_56;
                }
                Size = v31;
                v13 = BiEnumerateSubElements(
                        a1,
                        (int)Heap + 4,
                        Size_4,
                        a4,
                        (__int64)&v46,
                        (__int64)&Size,
                        (__int64)&v43,
                        a8,
                        a9 - 1);
                if ( (int)(v13 + 0x80000000) >= 0 && v13 != -1073741789 )
                {
                  if ( v13 == -1073741275 || v13 == -1073741772 )
                  {
                    v13 = 0;
                    goto LABEL_46;
                  }
                  BiLogMessage(4, L"Failed to enumerate subelements. Status: %x", (unsigned int)v13);
LABEL_71:
                  v38 = v54;
                  if ( v54 )
                    goto LABEL_77;
                  goto LABEL_78;
                }
                v33 = v10 + Size;
                if ( v10 + Size >= v10 )
                {
                  v13 = 0;
                  v10 += Size;
                  v34 = v43;
                  *a7 += v43;
                  if ( *a6 < v33 )
                  {
                    v16 = v46;
                    v35 = 0;
                    v40 = 0;
LABEL_57:
                    RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, Heap);
                    RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, P);
                    BiCloseKey(Handle);
                    v17 = v44;
                    Heap = 0;
                    P = 0;
                    Handle = 0;
                    goto LABEL_60;
                  }
                  if ( v34 )
                  {
                    v36 = (_QWORD *)v46;
                    v35 = *a6 - v33;
                    v16 = a5 + v33;
                    v46 = v16;
                    *v36 = v16;
                    v40 = v35;
                    v52 = v36;
                    goto LABEL_57;
                  }
LABEL_46:
                  v16 = v46;
LABEL_56:
                  v35 = v40;
                  goto LABEL_57;
                }
              }
            }
            v10 = -1;
            v13 = -1073741675;
            goto LABEL_71;
          }
          BiLogMessage(3, L"Dropping invalid data type. Element: %ws", v19);
        }
        v17 = v44;
        v13 = 0;
LABEL_59:
        v35 = v40;
        Heap = 0;
LABEL_60:
        v15 = v49 + 1;
        v49 = v15;
        if ( v15 >= v45 )
        {
          v38 = v54;
          if ( v54 )
          {
            Size = v35;
            v13 = BiEnumerateSubObjectElements(a1, (_DWORD)v54, v50, a4, v16, (__int64)&Size, (__int64)&v43, a8, a9 - 1);
            if ( (int)(v13 + 0x80000000) < 0 || v13 == -1073741789 )
            {
              if ( v10 + Size < v10 )
              {
                v10 = -1;
                v13 = -1073741675;
              }
              else
              {
                v13 = 0;
                v10 += Size;
                if ( v43 )
                {
                  v52 = 0;
                  *a7 += v43;
                }
              }
            }
            else
            {
              BiLogMessage(4, L"Failed to enumerate subobject elements. Status: %x", (unsigned int)v13);
            }
LABEL_77:
            RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v38);
LABEL_78:
            if ( Heap )
LABEL_79:
              RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, Heap);
          }
          if ( P )
            RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, P);
          if ( Handle )
            BiCloseKey(Handle);
          if ( v52 )
            *v52 = 0;
          goto LABEL_86;
        }
      }
      v22 = 3;
      goto LABEL_16;
    }
LABEL_86:
    v11 = v44;
  }
  if ( v53 )
    BiCloseKey(v53);
  v12 = a6;
  if ( *a6 < v10 )
    v13 = -1073741789;
  if ( v11 )
    RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v11);
LABEL_93:
  *v12 = v10;
  return (unsigned int)v13;
}

```

## disassembly

```asm
0x140019bb8  mov     rax, rsp
0x140019bbb  mov     [rax+18h], rbx
0x140019bbf  mov     [rax+20h], r9d
0x140019bc3  mov     [rax+10h], rdx
0x140019bc7  mov     [rax+8], rcx
0x140019bcb  push    rbp
0x140019bcc  push    rsi
0x140019bcd  push    rdi
0x140019bce  push    r12
0x140019bd0  push    r13
0x140019bd2  push    r14
0x140019bd4  push    r15
0x140019bd6  lea     rbp, [rax-3Fh]
0x140019bda  sub     rsp, 0C0h
0x140019be1  xor     r15d, r15d
0x140019be4  mov     ebx, r8d
0x140019be7  mov     rax, rdx
0x140019bea  mov     r8, [rbp+37h+arg_30]
0x140019bee  mov     esi, r15d
0x140019bf1  mov     [rbp+37h+var_50], r15
0x140019bf5  mov     r14d, r15d
0x140019bf8  mov     [rbp+37h+var_70], r15d
0x140019bfc  mov     [rbp+37h+var_94], r15d
0x140019c00  mov     [r8], r15d
0x140019c03  mov     [rbp+37h+var_88], r15d
0x140019c07  mov     [rbp+37h+Handle], r15
0x140019c0b  mov     [rbp+37h+P], r15
0x140019c0f  mov     [rbp+37h+var_90], r15
0x140019c13  cmp     [rbp+37h+arg_40], r15d
0x140019c1a  jg      short loc_140019C2A
0x140019c1c  mov     rbx, [rbp+37h+arg_28]
0x140019c20  mov     edi, 0C000000Dh
0x140019c25  jmp     loc_14001A23D
0x140019c2a  lea     r9, [rbp+37h+var_50]
0x140019c2e  mov     r8d, 20019h
0x140019c34  lea     rdx, aElements; "Elements"
0x140019c3b  mov     rcx, rax
0x140019c3e  call    BiOpenKey
0x140019c43  mov     edi, eax
0x140019c45  mov     r12d, 0C0000023h
0x140019c4b  test    eax, eax
0x140019c4d  js      loc_14001A205
0x140019c53  mov     rcx, [rbp+37h+var_50]
0x140019c57  lea     r8, [rbp+37h+var_88]
0x140019c5b  lea     rdx, [rbp+37h+var_90]
0x140019c5f  call    BiEnumerateSubKeys
0x140019c64  mov     edi, eax
0x140019c66  test    eax, eax
0x140019c68  jns     short loc_140019C83
0x140019c6a  mov     r8d, eax
0x140019c6d  lea     rdx, aFailedToEnumer_1; "Failed to enumerate subkeys. Status: %x"
0x140019c74  mov     ecx, 4
0x140019c79  call    BiLogMessage
0x140019c7e  jmp     loc_14001A201
0x140019c83  mov     eax, r15d
0x140019c86  mov     r13, [rbp+37h+arg_20]
0x140019c8a  mov     [rbp+37h+var_80], r13
0x140019c8e  mov     [rbp+37h+var_6C], eax
0x140019c91  mov     [rbp+37h+var_58], r15
0x140019c95  mov     [rbp+37h+var_48], r15
0x140019c99  mov     [rbp+37h+var_A0], r15d
0x140019c9d  mov     [rbp+37h+var_68], r15d
0x140019ca1  cmp     [rbp+37h+var_88], r15d
0x140019ca5  jbe     loc_14001A201
0x140019cab  mov     r12, [rbp+37h+var_90]
0x140019caf  mov     rcx, [rbp+37h+var_50]
0x140019cb3  lea     r9, [rbp+37h+Handle]
0x140019cb7  mov     r14d, eax
0x140019cba  mov     r8d, 20019h
0x140019cc0  mov     r15, [r12+r14*8]
0x140019cc4  mov     rdx, r15
0x140019cc7  mov     [rbp+37h+var_40], r15
0x140019ccb  call    BiOpenKey
0x140019cd0  mov     edi, eax
0x140019cd2  test    eax, eax
0x140019cd4  jns     short loc_140019CDD
0x140019cd6  xor     edi, edi
0x140019cd8  jmp     loc_14001A04C
0x140019cdd  mov     rcx, [r12+r14*8]; String
0x140019ce1  xor     edx, edx; EndPtr
0x140019ce3  lea     r8d, [rdx+10h]; Radix
0x140019ce7  call    cs:__imp_wcstoul
0x140019ced  mov     r14d, eax
0x140019cf0  mov     dword ptr [rbp+37h+Size+4], eax
0x140019cf3  dec     eax
0x140019cf5  cmp     eax, 0FFFFFFFDh
0x140019cf8  ja      loc_14001A03B
0x140019cfe  mov     r12d, r14d
0x140019d01  shr     r12d, 18h
0x140019d05  and     r12d, 0Fh
0x140019d09  mov     eax, r12d
0x140019d0c  sub     eax, 1
0x140019d0f  jz      short loc_140019D2C
0x140019d11  sub     eax, 1
0x140019d14  jz      loc_140019D9E
0x140019d1a  sub     eax, 1
0x140019d1d  jz      short loc_140019D9E
0x140019d1f  sub     eax, 1
0x140019d22  jz      short loc_140019D96
0x140019d24  sub     eax, 1
0x140019d27  jz      short loc_140019D2C
0x140019d29  sub     eax, 1
0x140019d2c  mov     r9d, 3
0x140019d32  mov     rcx, [rbp+37h+Handle]
0x140019d36  lea     rax, [rbp+37h+var_70]
0x140019d3a  mov     [rsp+0F0h+var_C8], rax
0x140019d3f  lea     rdx, aElement; "Element"
0x140019d46  lea     rax, [rbp+37h+P]
0x140019d4a  xor     r8d, r8d
0x140019d4d  mov     [rsp+0F0h+var_D0], rax
0x140019d52  call    BiGetRegistryValue
0x140019d57  mov     edi, eax
0x140019d59  cmp     eax, 0C0000034h
0x140019d5e  jz      short loc_140019D8B
0x140019d60  cmp     eax, 0C0000225h
0x140019d65  jz      short loc_140019D8B
0x140019d67  cmp     eax, 0C0000024h
0x140019d6c  jnz     short loc_140019DA6
0x140019d6e  cmp     r14d, 14000006h
0x140019d75  jnz     short loc_140019DA6
0x140019d77  mov     r8, r15
0x140019d7a  lea     rdx, aDroppingInvali; "Dropping invalid data type. Element: %w"...
0x140019d81  mov     ecx, 3
0x140019d86  call    BiLogMessage
0x140019d8b  mov     r12, [rbp+37h+var_90]
0x140019d8f  xor     edi, edi
0x140019d91  jmp     loc_14001A04C
0x140019d96  mov     r9d, 7
0x140019d9c  jmp     short loc_140019D32
0x140019d9e  mov     r9d, 1
0x140019da4  jmp     short loc_140019D32
0x140019da6  test    eax, eax
0x140019da8  js      loc_14001A136
0x140019dae  mov     r15, [rbp+37h+P]
0x140019db2  xor     r14d, r14d
0x140019db5  cmp     r12d, 1
0x140019db9  mov     edi, 200h
0x140019dbe  mov     eax, 100h
0x140019dc3  cmovnz  edi, eax
0x140019dc6  mov     dword ptr [rbp+37h+Size], edi
0x140019dc9  test    r14, r14
0x140019dcc  jz      short loc_140019DE6
0x140019dce  mov     rcx, gs:60h
0x140019dd7  mov     r8, r14; P
0x140019dda  xor     edx, edx; Flags
0x140019ddc  mov     rcx, [rcx+30h]; HeapHandle
0x140019de0  call    cs:__imp_RtlFreeHeap
0x140019de6  mov     rcx, gs:60h
0x140019def  xor     edx, edx; Flags
0x140019df1  mov     r8d, edi; Size
0x140019df4  mov     rcx, [rcx+30h]; HeapHandle
0x140019df8  call    cs:__imp_RtlAllocateHeap
0x140019dfe  mov     r14, rax
0x140019e01  test    rax, rax
0x140019e04  jz      loc_14001A12F
0x140019e0a  mov     r9d, dword ptr [rbp+37h+Size+4]
0x140019e0e  lea     rax, [rbp+37h+Size]
0x140019e12  mov     r8d, [rbp+37h+var_70]
0x140019e16  mov     rdx, r15
0x140019e19  mov     rcx, [rbp+37h+arg_8]
0x140019e1d  mov     [rsp+0F0h+var_C0], rax
0x140019e22  mov     eax, [rbp+37h+arg_18]
0x140019e25  mov     [rsp+0F0h+var_C8], r14
0x140019e2a  mov     dword ptr [rsp+0F0h+var_D0], eax
0x140019e2e  call    BiConvertRegistryDataToElement
0x140019e33  mov     edi, eax
0x140019e35  cmp     eax, 0C0000023h
0x140019e3a  jnz     short loc_140019E41
0x140019e3c  mov     edi, dword ptr [rbp+37h+Size]
0x140019e3f  jmp     short loc_140019DC9
0x140019e41  test    eax, eax
0x140019e43  js      loc_14001A115
0x140019e49  lea     eax, [rsi+18h]
0x140019e4c  cmp     eax, esi
0x140019e4e  jb      loc_14001A10B
0x140019e54  mov     r15d, dword ptr [rbp+37h+Size]
0x140019e58  lea     esi, [rax+r15]
0x140019e5c  cmp     esi, eax
0x140019e5e  jb      loc_14001A10B
0x140019e64  mov     rax, [rbp+37h+arg_30]
0x140019e68  inc     dword ptr [rax]
0x140019e6a  mov     rax, [rbp+37h+arg_28]
0x140019e6e  mov     edi, [rax]
0x140019e70  cmp     edi, esi
0x140019e72  jnb     short loc_140019E78
0x140019e74  xor     edi, edi
0x140019e76  jmp     short loc_140019EB6
0x140019e78  mov     eax, esi
0x140019e7a  lea     rcx, [r13+18h]; void *
0x140019e7e  add     rax, [rbp+37h+arg_20]
0x140019e82  mov     r8, r15; Size
0x140019e85  mov     [r13+0], rax
0x140019e89  mov     rdx, r14; Src
0x140019e8c  mov     eax, dword ptr [rbp+37h+Size+4]
0x140019e8f  mov     [r13+8], ebx
0x140019e93  mov     dword ptr [r13+0Ch], 1
0x140019e9b  mov     [r13+10h], eax
0x140019e9f  mov     [r13+14h], r15d
0x140019ea3  call    memcpy_0
0x140019ea8  mov     [rbp+37h+var_58], r13
0x140019eac  sub     edi, esi
0x140019eae  mov     r13, [r13+0]
0x140019eb2  mov     [rbp+37h+var_80], r13
0x140019eb6  mov     ecx, [rbp+37h+arg_18]
0x140019eb9  mov     [rbp+37h+var_A0], edi
0x140019ebc  test    cl, 8
0x140019ebf  jz      loc_140019FA0
0x140019ec5  cmp     r12d, 1
0x140019ec9  jnz     loc_140019FA0
0x140019ecf  mov     eax, [rbp+37h+arg_40]
0x140019ed5  lea     rdx, [r14+4]
0x140019ed9  mov     r8d, dword ptr [rbp+37h+Size+4]
0x140019edd  dec     eax
0x140019edf  mov     [rsp+40h], eax
0x140019ee3  mov     r9d, ecx
0x140019ee6  mov     rax, [rbp+37h+arg_38]
0x140019eea  mov     rcx, [rbp+37h+arg_0]
0x140019eee  mov     qword ptr [rsp+0F0h+var_B8], rax
0x140019ef3  lea     rax, [rbp+37h+var_94]
0x140019ef7  mov     [rsp+0F0h+var_C0], rax
0x140019efc  lea     rax, [rbp+37h+Size]
0x140019f00  mov     [rsp+0F0h+var_C8], rax
0x140019f05  lea     rax, [rbp+37h+var_80]
0x140019f09  mov     [rsp+0F0h+var_D0], rax
0x140019f0e  mov     dword ptr [rbp+37h+Size], edi
0x140019f11  call    BiEnumerateSubElements
0x140019f16  mov     ecx, 80000000h
0x140019f1b  mov     edi, eax
0x140019f1d  add     eax, ecx
0x140019f1f  test    ecx, eax
0x140019f21  jnz     short loc_140019F4A
0x140019f23  cmp     edi, 0C0000023h
0x140019f29  jz      short loc_140019F4A
0x140019f2b  cmp     edi, 0C0000225h
0x140019f31  jz      short loc_140019F3F
0x140019f33  cmp     edi, 0C0000034h
0x140019f39  jnz     loc_14001A0EB
0x140019f3f  xor     edi, edi
0x140019f41  mov     r13, [rbp+37h+var_80]
0x140019f45  jmp     loc_140019FEC
0x140019f4a  mov     ecx, dword ptr [rbp+37h+Size]
0x140019f4d  add     ecx, esi
0x140019f4f  cmp     ecx, esi
0x140019f51  jb      loc_14001A10B
0x140019f57  mov     r8, [rbp+37h+arg_30]
0x140019f5b  xor     edi, edi
0x140019f5d  mov     rdx, [rbp+37h+arg_28]
0x140019f61  mov     esi, ecx
0x140019f63  mov     eax, [rbp+37h+var_94]
0x140019f66  add     [r8], eax
0x140019f69  cmp     [rdx], ecx
0x140019f6b  jnb     short loc_140019F7A
0x140019f6d  mov     r13, [rbp+37h+var_80]
0x140019f71  xor     r15d, r15d
0x140019f74  mov     [rbp+37h+var_A0], r15d
0x140019f78  jmp     short loc_140019FF0
0x140019f7a  test    eax, eax
0x140019f7c  jz      short loc_140019F41
0x140019f7e  mov     r15d, [rdx]
0x140019f81  mov     rdx, [rbp+37h+var_80]
0x140019f85  sub     r15d, ecx
0x140019f88  mov     r13d, ecx
0x140019f8b  add     r13, [rbp+37h+arg_20]
0x140019f8f  mov     [rbp+37h+var_80], r13
0x140019f93  mov     [rdx], r13
0x140019f96  mov     [rbp+37h+var_A0], r15d
0x140019f9a  mov     [rbp+37h+var_58], rdx
0x140019f9e  jmp     short loc_140019FF0
0x140019fa0  xor     edi, edi
0x140019fa2  test    cl, 4
0x140019fa5  jz      short loc_140019FEC
0x140019fa7  cmp     dword ptr [rbp+37h+Size+4], 14000006h
0x140019fae  jnz     short loc_140019FEC
0x140019fb0  mov     rcx, gs:60h
0x140019fb9  mov     r8, r15; Size
0x140019fbc  xor     edx, edx; Flags
0x140019fbe  mov     rcx, [rcx+30h]; HeapHandle
0x140019fc2  call    cs:__imp_RtlAllocateHeap
0x140019fc8  mov     [rbp+37h+var_48], rax
0x140019fcc  test    rax, rax
0x140019fcf  jz      loc_14001A101
0x140019fd5  mov     r8, r15; Size
0x140019fd8  mov     rdx, r14; Src
0x140019fdb  mov     rcx, rax; void *
0x140019fde  call    memcpy_0
0x140019fe3  mov     eax, r15d
0x140019fe6  shr     eax, 4
0x140019fe9  mov     [rbp+37h+var_68], eax
0x140019fec  mov     r15d, [rbp+37h+var_A0]
0x140019ff0  mov     rcx, gs:60h
0x140019ff9  mov     r8, r14; P
0x140019ffc  xor     edx, edx; Flags
0x140019ffe  mov     rcx, [rcx+30h]; HeapHandle
0x14001a002  call    cs:__imp_RtlFreeHeap
0x14001a008  mov     rcx, gs:60h
0x14001a011  xor     edx, edx; Flags
0x14001a013  mov     r8, [rbp+37h+P]; P
0x14001a017  mov     rcx, [rcx+30h]; HeapHandle
0x14001a01b  call    cs:__imp_RtlFreeHeap
0x14001a021  mov     rcx, [rbp+37h+Handle]; Handle
  ... truncated ...
```
