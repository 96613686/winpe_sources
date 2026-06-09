# Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::InitializeResMessage(HINSTANCE__ *,int,...)

- ea: `0x1400127f0`
- end: `0x14001295b`
- name: `?InitializeResMessage@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@QEAAJPEAUHINSTANCE__@@HZZ`
- size: `363`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x140014fdc`

## callees

- `0x1400126fc`
- `0x1400127f0`
- `0x14001ca80`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!LockResource` at `0x140012870`
- `api-ms-win-core-libraryloader-l1-2-0!LockResource` at `0x140012870`
- `api-ms-win-core-libraryloader-l1-2-0!FindResourceExW` at `0x140012849`
- `api-ms-win-core-libraryloader-l1-2-0!FindResourceExW` at `0x140012849`
- `api-ms-win-core-libraryloader-l1-2-0!LoadResource` at `0x14001285e`
- `api-ms-win-core-libraryloader-l1-2-0!LoadResource` at `0x14001285e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x140012942`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x140012942`

## pseudocode

```c
__int64 Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::InitializeResMessage(
        __int64 a1,
        HMODULE a2,
        unsigned int a3,
        ...)
{
  char v4; // bl
  void *v6; // rdi
  unsigned int v7; // ebp
  HRSRC Resource; // rax
  HGLOBAL v9; // rax
  _WORD *v10; // rax
  unsigned int v11; // edx
  unsigned int v12; // ebx
  const OLECHAR *v13; // rsi
  unsigned __int64 v14; // rbx
  unsigned __int64 v15; // r14
  int v16; // eax
  unsigned __int64 v17; // rdx
  _WORD *v18; // rax
  _WORD *v19; // rcx
  _QWORD v21[12]; // [rsp+28h] [rbp-60h] BYREF
  va_list va; // [rsp+A8h] [rbp+20h] BYREF

  va_start(va, a3);
  memset(v21, 0, 24);
  v4 = a3;
  v6 = 0;
  v7 = -2147467259;
  Resource = FindResourceExW(a2, (LPCWSTR)6, (LPCWSTR)(unsigned __int16)((a3 >> 4) + 1), 0);
  if ( Resource )
  {
    v9 = LoadResource(a2, Resource);
    if ( v9 )
    {
      v10 = LockResource(v9);
      if ( v10 )
      {
        v11 = 0;
        v12 = v4 & 0xF;
        if ( v12 )
        {
          do
          {
            ++v11;
            v10 += (unsigned __int16)*v10 + 1;
          }
          while ( v11 < v12 );
        }
        v13 = v10 + 1;
        if ( !*v10 )
          v13 = &SubKey;
        if ( !v13 )
          goto LABEL_23;
        v14 = -1;
        do
          ++v14;
        while ( v13[v14] );
        v15 = (unsigned __int16)*v10;
        if ( v15 < v14 )
          v14 = (unsigned __int16)*v10;
        v16 = Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_EnsureCapacity(
                (__int64)v21,
                (unsigned __int16)*v10);
        v6 = (void *)v21[0];
        v7 = v16;
        if ( v16 >= 0 )
        {
          if ( v14 <= 0x7FFFFFFE )
          {
            v17 = v15 + 1;
            v18 = (_WORD *)v21[0];
            do
            {
              if ( !v14 )
                break;
              if ( !*v13 )
                break;
              *v18++ = *v13++;
              --v14;
              --v17;
            }
            while ( v17 );
            v19 = v18 - 1;
            if ( v17 )
              v19 = v18;
            *v19 = 0;
          }
          else
          {
            *(_WORD *)v21[0] = 0;
          }
LABEL_23:
          v7 = Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::InitializeMessage(
                 a1,
                 v6,
                 va);
        }
      }
    }
  }
  if ( v6 )
    CoTaskMemFree(v6);
  return v7;
}

```

## disassembly

```asm
0x1400127f0  mov     rax, rsp
0x1400127f3  mov     [rax+18h], r8d
0x1400127f7  mov     [rax+20h], r9
0x1400127fb  push    rbx
0x1400127fc  push    rbp
0x1400127fd  push    rsi
0x1400127fe  push    rdi
0x1400127ff  push    r12
0x140012801  push    r13
0x140012803  push    r14
0x140012805  push    r15
0x140012807  sub     rsp, 48h
0x14001280b  xor     r12d, r12d
0x14001280e  mov     rsi, rdx
0x140012811  mov     [rax-60h], r12
0x140012815  mov     ebx, r8d
0x140012818  mov     [rax-58h], r12
0x14001281c  mov     r15, rcx
0x14001281f  mov     [rax-50h], r12
0x140012823  xor     r9d, r9d; wLanguage
0x140012826  mov     eax, r8d
0x140012829  lea     r13d, [r12+1]
0x14001282e  shr     eax, 4
0x140012831  lea     edx, [r12+6]; lpType
0x140012836  add     ax, r13w
0x14001283a  mov     rcx, rsi; hModule
0x14001283d  movzx   r8d, ax; lpName
0x140012841  mov     edi, r12d
0x140012844  mov     ebp, 80004005h
0x140012849  call    cs:__imp_FindResourceExW
0x14001284f  test    rax, rax
0x140012852  jz      loc_14001293A
0x140012858  mov     rdx, rax; hResInfo
0x14001285b  mov     rcx, rsi; hModule
0x14001285e  call    cs:__imp_LoadResource
0x140012864  test    rax, rax
0x140012867  jz      loc_14001293A
0x14001286d  mov     rcx, rax; hResData
0x140012870  call    cs:__imp_LockResource
0x140012876  test    rax, rax
0x140012879  jz      loc_14001293A
0x14001287f  mov     edx, r12d
0x140012882  and     ebx, 0Fh
0x140012885  jbe     short loc_140012899
0x140012887  movzx   ecx, word ptr [rax]
0x14001288a  add     edx, r13d
0x14001288d  lea     rax, [rax+rcx*2]
0x140012891  add     rax, 2
0x140012895  cmp     edx, ebx
0x140012897  jb      short loc_140012887
0x140012899  lea     rsi, [rax+2]
0x14001289d  cmp     [rax], r12w
0x1400128a1  jnz     short loc_1400128AA
0x1400128a3  lea     rsi, SubKey
0x1400128aa  test    rsi, rsi
0x1400128ad  jz      short loc_140012925
0x1400128af  or      rbx, 0FFFFFFFFFFFFFFFFh
0x1400128b3  inc     rbx
0x1400128b6  cmp     [rsi+rbx*2], r12w
0x1400128bb  jnz     short loc_1400128B3
0x1400128bd  movzx   r14d, word ptr [rax]
0x1400128c1  lea     rcx, [rsp+88h+var_60]
0x1400128c6  cmp     r14, rbx
0x1400128c9  mov     edx, r14d
0x1400128cc  cmovb   rbx, r14
0x1400128d0  call    ?_EnsureCapacity@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAJ_K@Z; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_EnsureCapacity(unsigned __int64)
0x1400128d5  mov     rdi, [rsp+88h+var_60]
0x1400128da  mov     ebp, eax
0x1400128dc  test    eax, eax
0x1400128de  js      short loc_14001293A
0x1400128e0  cmp     rbx, 7FFFFFFEh
0x1400128e7  jbe     short loc_1400128EF
0x1400128e9  mov     [rdi], r12w
0x1400128ed  jmp     short loc_140012925
0x1400128ef  lea     rdx, [r14+1]
0x1400128f3  mov     rax, rdi
0x1400128f6  test    rbx, rbx
0x1400128f9  jz      short loc_140012916
0x1400128fb  movzx   ecx, word ptr [rsi]
0x1400128fe  test    cx, cx
0x140012901  jz      short loc_140012916
0x140012903  mov     [rax], cx
0x140012906  add     rsi, 2
0x14001290a  add     rax, 2
0x14001290e  sub     rbx, r13
0x140012911  sub     rdx, r13
0x140012914  jnz     short loc_1400128F6
0x140012916  test    rdx, rdx
0x140012919  lea     rcx, [rax-2]
0x14001291d  cmovnz  rcx, rax
0x140012921  mov     [rcx], r12w
0x140012925  lea     r8, [rsp+88h+arg_18]
0x14001292d  mov     rdx, rdi
0x140012930  mov     rcx, r15
0x140012933  call    ?InitializeMessage@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@QEAAJPEBGPEAD@Z; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::InitializeMessage(ushort const *,char *)
0x140012938  mov     ebp, eax
0x14001293a  test    rdi, rdi
0x14001293d  jz      short loc_140012948
0x14001293f  mov     rcx, rdi; pv
0x140012942  call    cs:__imp_CoTaskMemFree
0x140012948  mov     eax, ebp
0x14001294a  add     rsp, 48h
0x14001294e  pop     r15
0x140012950  pop     r14
0x140012952  pop     r13
0x140012954  pop     r12
0x140012956  pop     rdi
0x140012957  pop     rsi
0x140012958  pop     rbp
0x140012959  pop     rbx
0x14001295a  retn
```
