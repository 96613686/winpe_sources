# CGenerate::CreateObjectList(int)

- ea: `0x14000c178`
- end: `0x14000c5a8`
- name: `?CreateObjectList@CGenerate@@AEAAJH@Z`
- size: `1072`
- prototype: `__int64 __fastcall(CGenerate *__hidden this, int)`
- caller_count: `1`
- callee_count: `7`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x14000c5b0`

## callees

- `0x140006d24`
- `0x140008b28`
- `0x14000a460`
- `0x14000ac48`
- `0x14000c178`
- `0x14000d8b4`
- `0x14000d94c`

## import_xrefs

- `wbemcomn!Throttle` at `0x14000c4e4`
- `wbemcomn!Throttle` at `0x14000c4e4`
- `wbemcomn!?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z` at `0x14000c298`
- `wbemcomn!?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z` at `0x14000c2ad`
- `wbemcomn!?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z` at `0x14000c340`
- `wbemcomn!?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z` at `0x14000c40c`
- `wbemcomn!?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z` at `0x14000c4a1`
- `wbemcomn!?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z` at `0x14000c298`
- `wbemcomn!?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z` at `0x14000c2ad`
- `wbemcomn!?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z` at `0x14000c340`
- `wbemcomn!?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z` at `0x14000c40c`
- `wbemcomn!?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z` at `0x14000c4a1`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x14000c2c2`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x14000c2c2`

## pseudocode

```c
__int64 __fastcall CGenerate::CreateObjectList(CGenerate *this, int a2)
{
  CGenerate *v2; // r14
  CGenerate *v3; // rcx
  int appended; // edi
  CGenerate *v5; // r12
  HINSTANCE ResourceDll; // r13
  const unsigned __int16 *Name; // rax
  unsigned __int16 *v8; // r12
  const unsigned __int16 *StringSystem; // rax
  unsigned __int16 *v10; // rbx
  __int64 v11; // r8
  const unsigned __int16 *v12; // rax
  unsigned __int16 *v13; // rbx
  unsigned int i; // r12d
  __int64 v15; // rax
  unsigned int v16; // eax
  unsigned int j; // r13d
  CGenerate *v18; // rcx
  unsigned __int16 *NameInd; // rdi
  __int64 v20; // rcx
  _QWORD *k; // rax
  _QWORD *v22; // rbx
  unsigned __int16 *v24; // [rsp+48h] [rbp-60h]
  CGenerate *v25; // [rsp+50h] [rbp-58h]
  CGenerate *v26; // [rsp+60h] [rbp-48h]
  unsigned int v29; // [rsp+C0h] [rbp+18h]
  unsigned int v30; // [rsp+C8h] [rbp+20h]

  v2 = this;
  appended = CGenerate::AppendString(this, L"[objects]\r\n", 1);
  if ( appended < 0 )
    return (unsigned int)appended;
  try
  {
    v29 = 0;
    v5 = (CGenerate *)((char *)v2 + 92);
    v25 = (CGenerate *)((char *)v2 + 92);
    if ( *((_DWORD *)v2 + 23) == 2 )
    {
      ResourceDll = GetResourceDll();
      if ( ResourceDll )
      {
        Name = CGenerate::GenerateName(v3, L"WMI_Objects", *((_DWORD *)v2 + 21));
        v8 = (unsigned __int16 *)Name;
        if ( Name )
        {
          appended = CGenerate::AppendString(v2, Name, 1);
          if ( appended >= 0 )
          {
            appended = CGenerate::AppendString(v2, L"NAME", 1);
            if ( appended >= 0 )
            {
              appended = CGenerate::AppendString(v2, L"=", 1);
              if ( appended >= 0 )
              {
                StringSystem = LoadStringSystem(ResourceDll, 0xCCu);
                v10 = (unsigned __int16 *)StringSystem;
                if ( StringSystem )
                {
                  appended = CGenerate::AppendString(v2, StringSystem, 1);
                  if ( appended >= 0 )
                    appended = CGenerate::AppendString(v2, L"\r\n", 1);
                  CWin32DefaultArena::WbemMemFree(v10);
                }
                else
                {
                  appended = -2147024882;
                }
              }
            }
          }
          CWin32DefaultArena::WbemMemFree(v8);
        }
        else
        {
          appended = -2147024882;
        }
        FreeLibrary(ResourceDll);
        v5 = (CGenerate *)((char *)v2 + 92);
      }
      else
      {
        appended = -2147467259;
      }
      v11 = 1;
      if ( appended < 0 )
        goto LABEL_27;
    }
    else
    {
      v11 = 0;
    }
    v12 = CGenerate::GenerateName(v3, L"WMI_Objects", *((_DWORD *)v2 + v11 + 21));
    v13 = (unsigned __int16 *)v12;
    if ( v12 )
    {
      appended = CGenerate::AppendString(v2, v12, 1);
      if ( appended >= 0 )
      {
        appended = CGenerate::AppendString(v2, L"NAME=WMI Objects", 1);
        if ( appended >= 0 )
          appended = CGenerate::AppendString(v2, L"\r\n", 1);
      }
      CWin32DefaultArena::WbemMemFree(v13);
    }
    else
    {
      appended = -2147024882;
    }
LABEL_27:
    v26 = v5;
    for ( i = 0; i < *((_DWORD *)v2 + 20) && appended >= 0; ++i )
    {
      v15 = 5LL * i;
      if ( *((_QWORD *)v2 + 5 * i + 4) )
      {
        try
        {
          v22 = (_QWORD *)**((_QWORD **)v2 + 5 * i + 3);
          while ( v22 != *((_QWORD **)v2 + v15 + 3) && appended >= 0 )
          {
            v16 = *(_DWORD *)(v22[5] + 32LL);
            v30 = v16;
            for ( j = 0; j < *(_DWORD *)v25 && appended >= 0 && j < v16; ++j )
            {
              NameInd = CGenerate::GenerateNameInd(v25, *(const unsigned __int16 **)(v22[5] + 8LL), v29);
              if ( NameInd
                && (v24 = CGenerate::GenerateName(v18, NameInd, *((_DWORD *)v2 + j + 21)),
                    CWin32DefaultArena::WbemMemFree(NameInd),
                    v24) )
              {
                appended = CGenerate::AppendString(v2, v24, 1);
                if ( appended >= 0 )
                {
                  appended = CGenerate::AppendString(v2, L"NAME", 1);
                  if ( appended >= 0 )
                  {
                    appended = CGenerate::AppendString(v2, L"=", 1);
                    if ( appended >= 0 )
                    {
                      appended = CGenerate::AppendString(
                                   v2,
                                   *(const unsigned __int16 **)(*(_QWORD *)(*(_QWORD *)(v22[5] + 24LL) + 8LL * j) + 8LL),
                                   1);
                      if ( appended >= 0 )
                        appended = CGenerate::AppendString(v2, L"\r\n", 1);
                    }
                  }
                }
                CWin32DefaultArena::WbemMemFree(v24);
              }
              else
              {
                appended = -2147024882;
              }
              v16 = v30;
            }
            if ( a2 && appended >= 0 )
              Throttle(3u, 0x3E8u, 0x64u, 0xAu, 0xBB8u);
            if ( !*((_BYTE *)v22 + 25) )
            {
              v20 = v22[2];
              if ( *(_BYTE *)(v20 + 25) )
              {
                for ( k = (_QWORD *)v22[1]; !*((_BYTE *)k + 25) && v22 == (_QWORD *)k[2]; k = (_QWORD *)k[1] )
                  v22 = k;
              }
              else
              {
                k = std::_Tree_val<std::_Tree_simple_types<std::pair<unsigned short * const,CObject *>>>::_Min((_QWORD *)v20);
              }
              v22 = k;
            }
            ++v29;
            v15 = 5LL * i;
          }
        }
        catch ( ... )
        {
          v2 = this;
          appended = -2147418113;
          v25 = v26;
          continue;
        }
      }
    }
  }
  catch ( ... )
  {
    return (unsigned int)-2147418113;
  }
  if ( appended >= 0 )
  {
    appended = CGenerate::AppendString(v2, L"\r\n", 1);
    if ( appended >= 0 )
      return (unsigned int)CGenerate::AppendString(v2, L"[text]\r\n", 1);
  }
  return (unsigned int)appended;
}

```

## disassembly

```asm
0x14000c178  mov     [rsp+arg_8], edx
0x14000c17c  mov     [rsp+arg_0], rcx
0x14000c181  push    rbx
0x14000c182  push    rsi
0x14000c183  push    rdi
0x14000c184  push    r12
0x14000c186  push    r13
0x14000c188  push    r14
0x14000c18a  push    r15
0x14000c18c  sub     rsp, 70h
0x14000c190  mov     r14, rcx
0x14000c193  mov     r15d, 1
0x14000c199  mov     r8d, r15d; int
0x14000c19c  lea     rdx, aObjects; "[objects]\r\n"
0x14000c1a3  call    ?AppendString@CGenerate@@AEAAJPEBGH@Z; CGenerate::AppendString(ushort const *,int)
0x14000c1a8  mov     edi, eax
0x14000c1aa  xor     esi, esi
0x14000c1ac  test    eax, eax
0x14000c1ae  js      loc_14000C596
0x14000c1b4  mov     [rsp+0A8h+arg_10], esi
0x14000c1bb  mov     [rsp+0A8h+var_70], rsi
0x14000c1c0  mov     [rsp+0A8h+var_68], rsi
0x14000c1c5  lea     r12, [r14+5Ch]
0x14000c1c9  mov     [rsp+0A8h+var_58], r12
0x14000c1ce  cmp     dword ptr [r12], 2
0x14000c1d3  jnz     loc_14000C2DC
0x14000c1d9  call    ?GetResourceDll@@YAPEAUHINSTANCE__@@XZ; GetResourceDll(void)
0x14000c1de  mov     r13, rax
0x14000c1e1  test    rax, rax
0x14000c1e4  jz      loc_14000C2CE
0x14000c1ea  mov     r8d, [r14+54h]; unsigned int
0x14000c1ee  lea     rdx, aWmiObjects; "WMI_Objects"
0x14000c1f5  call    ?GenerateName@CGenerate@@AEAAPEAGPEBGK@Z; CGenerate::GenerateName(ushort const *,ulong)
0x14000c1fa  mov     r12, rax
0x14000c1fd  mov     [rsp+0A8h+var_70], rax
0x14000c202  test    rax, rax
0x14000c205  jz      loc_14000C2BA
0x14000c20b  mov     r8d, r15d; int
0x14000c20e  mov     rdx, rax; unsigned __int16 *
0x14000c211  mov     rcx, r14; this
0x14000c214  call    ?AppendString@CGenerate@@AEAAJPEBGH@Z; CGenerate::AppendString(ushort const *,int)
0x14000c219  mov     edi, eax
0x14000c21b  test    eax, eax
0x14000c21d  js      loc_14000C2AA
0x14000c223  mov     r8d, r15d; int
0x14000c226  lea     rdx, aName; "NAME"
0x14000c22d  mov     rcx, r14; this
0x14000c230  call    ?AppendString@CGenerate@@AEAAJPEBGH@Z; CGenerate::AppendString(ushort const *,int)
0x14000c235  mov     edi, eax
0x14000c237  test    eax, eax
0x14000c239  js      short loc_14000C2AA
0x14000c23b  mov     r8d, r15d; int
0x14000c23e  lea     rdx, asc_14001B498; "="
0x14000c245  mov     rcx, r14; this
0x14000c248  call    ?AppendString@CGenerate@@AEAAJPEBGH@Z; CGenerate::AppendString(ushort const *,int)
0x14000c24d  mov     edi, eax
0x14000c24f  test    eax, eax
0x14000c251  js      short loc_14000C2AA
0x14000c253  mov     edx, 0CCh; uID
0x14000c258  mov     rcx, r13; hInstance
0x14000c25b  call    ?LoadStringSystem@@YAPEAGPEAUHINSTANCE__@@I@Z; LoadStringSystem(HINSTANCE__ *,uint)
0x14000c260  mov     rbx, rax
0x14000c263  mov     [rsp+0A8h+var_68], rax
0x14000c268  test    rax, rax
0x14000c26b  jz      short loc_14000C2A5
0x14000c26d  mov     r8d, r15d; int
0x14000c270  mov     rdx, rax; unsigned __int16 *
0x14000c273  mov     rcx, r14; this
0x14000c276  call    ?AppendString@CGenerate@@AEAAJPEBGH@Z; CGenerate::AppendString(ushort const *,int)
0x14000c27b  mov     edi, eax
0x14000c27d  test    eax, eax
0x14000c27f  js      short loc_14000C295
0x14000c281  mov     r8d, r15d; int
0x14000c284  lea     rdx, asc_14001B440; "\r\n"
0x14000c28b  mov     rcx, r14; this
0x14000c28e  call    ?AppendString@CGenerate@@AEAAJPEBGH@Z; CGenerate::AppendString(ushort const *,int)
0x14000c293  mov     edi, eax
0x14000c295  mov     rcx, rbx
0x14000c298  call    cs:__imp_?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z; CWin32DefaultArena::WbemMemFree(void *)
0x14000c29e  mov     [rsp+0A8h+var_68], rsi
0x14000c2a3  jmp     short loc_14000C2AA
0x14000c2a5  mov     edi, 8007000Eh
0x14000c2aa  mov     rcx, r12
0x14000c2ad  call    cs:__imp_?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z; CWin32DefaultArena::WbemMemFree(void *)
0x14000c2b3  mov     [rsp+0A8h+var_70], rsi
0x14000c2b8  jmp     short loc_14000C2BF
0x14000c2ba  mov     edi, 8007000Eh
0x14000c2bf  mov     rcx, r13; hLibModule
0x14000c2c2  call    cs:__imp_FreeLibrary
0x14000c2c8  lea     r12, [r14+5Ch]
0x14000c2cc  jmp     short loc_14000C2D3
0x14000c2ce  mov     edi, 80004005h
0x14000c2d3  mov     r8, r15
0x14000c2d6  test    edi, edi
0x14000c2d8  jns     short loc_14000C2DF
0x14000c2da  jmp     short loc_14000C352
0x14000c2dc  mov     r8, rsi
0x14000c2df  mov     r8d, [r14+r8*4+54h]; unsigned int
0x14000c2e4  lea     rdx, aWmiObjects; "WMI_Objects"
0x14000c2eb  call    ?GenerateName@CGenerate@@AEAAPEAGPEBGK@Z; CGenerate::GenerateName(ushort const *,ulong)
0x14000c2f0  mov     rbx, rax
0x14000c2f3  mov     [rsp+0A8h+var_70], rax
0x14000c2f8  test    rax, rax
0x14000c2fb  jz      short loc_14000C34D
0x14000c2fd  mov     r8d, r15d; int
0x14000c300  mov     rdx, rax; unsigned __int16 *
0x14000c303  mov     rcx, r14; this
0x14000c306  call    ?AppendString@CGenerate@@AEAAJPEBGH@Z; CGenerate::AppendString(ushort const *,int)
0x14000c30b  mov     edi, eax
0x14000c30d  test    eax, eax
0x14000c30f  js      short loc_14000C33D
0x14000c311  mov     r8d, r15d; int
0x14000c314  lea     rdx, aNameWmiObjects; "NAME=WMI Objects"
0x14000c31b  mov     rcx, r14; this
0x14000c31e  call    ?AppendString@CGenerate@@AEAAJPEBGH@Z; CGenerate::AppendString(ushort const *,int)
0x14000c323  mov     edi, eax
0x14000c325  test    eax, eax
0x14000c327  js      short loc_14000C33D
0x14000c329  mov     r8d, r15d; int
0x14000c32c  lea     rdx, asc_14001B440; "\r\n"
0x14000c333  mov     rcx, r14; this
0x14000c336  call    ?AppendString@CGenerate@@AEAAJPEBGH@Z; CGenerate::AppendString(ushort const *,int)
0x14000c33b  mov     edi, eax
0x14000c33d  mov     rcx, rbx
0x14000c340  call    cs:__imp_?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z; CWin32DefaultArena::WbemMemFree(void *)
0x14000c346  mov     [rsp+0A8h+var_70], rsi
0x14000c34b  jmp     short loc_14000C352
0x14000c34d  mov     edi, 8007000Eh
0x14000c352  mov     [rsp+0A8h+var_48], r12
0x14000c357  mov     r12d, esi
0x14000c35a  mov     [rsp+0A8h+var_78], r12d
0x14000c35f  cmp     r12d, [r14+50h]
0x14000c363  jnb     loc_14000C55D
0x14000c369  test    edi, edi
0x14000c36b  js      loc_14000C55D
0x14000c371  mov     eax, r12d
0x14000c374  lea     rax, [rax+rax*4]
0x14000c378  mov     [rsp+0A8h+var_50], rax
0x14000c37d  cmp     [r14+rax*8+20h], rsi
0x14000c382  jz      loc_14000C555
0x14000c388  mov     rbx, [r14+rax*8+18h]
0x14000c38d  mov     rbx, [rbx]
0x14000c390  cmp     rbx, [r14+rax*8+18h]
0x14000c395  jz      loc_14000C52F
0x14000c39b  test    edi, edi
0x14000c39d  js      loc_14000C52F
0x14000c3a3  mov     rax, [rbx+28h]
0x14000c3a7  mov     eax, [rax+20h]
0x14000c3aa  mov     [rsp+0A8h+arg_18], eax
0x14000c3b1  mov     r13d, esi
0x14000c3b4  mov     rcx, [rsp+0A8h+var_58]; this
0x14000c3b9  cmp     r13d, [rcx]
0x14000c3bc  jnb     loc_14000C4BD
0x14000c3c2  test    edi, edi
0x14000c3c4  js      loc_14000C4BD
0x14000c3ca  cmp     r13d, eax
0x14000c3cd  jnb     loc_14000C4BD
0x14000c3d3  mov     rdx, [rbx+28h]
0x14000c3d7  mov     r8d, [rsp+0A8h+arg_10]; unsigned int
0x14000c3df  mov     rdx, [rdx+8]; unsigned __int16 *
0x14000c3e3  call    ?GenerateNameInd@CGenerate@@AEAAPEAGPEBGK@Z; CGenerate::GenerateNameInd(ushort const *,ulong)
0x14000c3e8  mov     rdi, rax
0x14000c3eb  test    rax, rax
0x14000c3ee  jz      loc_14000C4A9
0x14000c3f4  mov     eax, r13d
0x14000c3f7  mov     r8d, [r14+rax*4+54h]; unsigned int
0x14000c3fc  mov     rdx, rdi; unsigned __int16 *
0x14000c3ff  call    ?GenerateName@CGenerate@@AEAAPEAGPEBGK@Z; CGenerate::GenerateName(ushort const *,ulong)
0x14000c404  mov     [rsp+0A8h+var_60], rax
0x14000c409  mov     rcx, rdi
0x14000c40c  call    cs:__imp_?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z; CWin32DefaultArena::WbemMemFree(void *)
0x14000c412  mov     rax, [rsp+0A8h+var_60]
0x14000c417  test    rax, rax
0x14000c41a  jz      loc_14000C4A9
0x14000c420  mov     r8d, r15d; int
0x14000c423  mov     rdx, rax; unsigned __int16 *
0x14000c426  mov     rcx, r14; this
0x14000c429  call    ?AppendString@CGenerate@@AEAAJPEBGH@Z; CGenerate::AppendString(ushort const *,int)
0x14000c42e  mov     edi, eax
0x14000c430  test    eax, eax
0x14000c432  js      short loc_14000C49C
0x14000c434  mov     r8d, r15d; int
0x14000c437  lea     rdx, aName; "NAME"
0x14000c43e  mov     rcx, r14; this
0x14000c441  call    ?AppendString@CGenerate@@AEAAJPEBGH@Z; CGenerate::AppendString(ushort const *,int)
0x14000c446  mov     edi, eax
0x14000c448  test    eax, eax
0x14000c44a  js      short loc_14000C49C
0x14000c44c  mov     r8d, r15d; int
0x14000c44f  lea     rdx, asc_14001B498; "="
0x14000c456  mov     rcx, r14; this
0x14000c459  call    ?AppendString@CGenerate@@AEAAJPEBGH@Z; CGenerate::AppendString(ushort const *,int)
0x14000c45e  mov     edi, eax
0x14000c460  test    eax, eax
0x14000c462  js      short loc_14000C49C
0x14000c464  mov     rax, [rbx+28h]
0x14000c468  mov     rcx, [rax+18h]
0x14000c46c  mov     edx, r13d
0x14000c46f  mov     rdx, [rcx+rdx*8]
0x14000c473  mov     r8d, r15d; int
0x14000c476  mov     rdx, [rdx+8]; unsigned __int16 *
0x14000c47a  mov     rcx, r14; this
0x14000c47d  call    ?AppendString@CGenerate@@AEAAJPEBGH@Z; CGenerate::AppendString(ushort const *,int)
0x14000c482  mov     edi, eax
0x14000c484  test    eax, eax
0x14000c486  js      short loc_14000C49C
0x14000c488  mov     r8d, r15d; int
0x14000c48b  lea     rdx, asc_14001B440; "\r\n"
0x14000c492  mov     rcx, r14; this
0x14000c495  call    ?AppendString@CGenerate@@AEAAJPEBGH@Z; CGenerate::AppendString(ushort const *,int)
0x14000c49a  mov     edi, eax
0x14000c49c  mov     rcx, [rsp+0A8h+var_60]
0x14000c4a1  call    cs:__imp_?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z; CWin32DefaultArena::WbemMemFree(void *)
0x14000c4a7  jmp     short loc_14000C4AE
0x14000c4a9  mov     edi, 8007000Eh
0x14000c4ae  add     r13d, r15d
0x14000c4b1  mov     eax, [rsp+0A8h+arg_18]
0x14000c4b8  jmp     loc_14000C3B4
0x14000c4bd  cmp     [rsp+0A8h+arg_8], esi
0x14000c4c4  jz      short loc_14000C4EA
0x14000c4c6  test    edi, edi
0x14000c4c8  js      short loc_14000C4EA
0x14000c4ca  mov     [rsp+0A8h+var_88], 0BB8h
0x14000c4d2  mov     edx, 3E8h
0x14000c4d7  mov     ecx, 3
0x14000c4dc  lea     r9d, [rcx+7]
0x14000c4e0  lea     r8d, [rcx+61h]
0x14000c4e4  call    cs:__imp_?Throttle@@YAJKKKKK@Z; Throttle(ulong,ulong,ulong,ulong,ulong)
0x14000c4ea  cmp     [rbx+19h], sil
0x14000c4ee  jnz     short loc_14000C51D
0x14000c4f0  mov     rcx, [rbx+10h]
0x14000c4f4  cmp     [rcx+19h], sil
0x14000c4f8  jnz     short loc_14000C501
0x14000c4fa  call    ?_Min@?$_Tree_val@U?$_Tree_simple_types@U?$pair@QEAGPEAVCObject@@@std@@@std@@@std@@SAPEAU?$_Tree_node@U?$pair@QEAGPEAVCObject@@@std@@PEAX@2@PEAU32@@Z; std::_Tree_val<std::_Tree_simple_types<std::pair<ushort * const,CObject *>>>::_Min(std::_Tree_node<std::pair<ushort * const,CObject *>,void *> *)
0x14000c4ff  jmp     short loc_14000C51A
0x14000c501  mov     rax, [rbx+8]
0x14000c505  jmp     short loc_14000C514
0x14000c507  cmp     rbx, [rax+10h]
0x14000c50b  jnz     short loc_14000C51A
0x14000c50d  mov     rbx, rax
0x14000c510  mov     rax, [rax+8]
0x14000c514  cmp     [rax+19h], sil
0x14000c518  jz      short loc_14000C507
0x14000c51a  mov     rbx, rax
0x14000c51d  add     [rsp+0A8h+arg_10], r15d
0x14000c525  mov     rax, [rsp+0A8h+var_50]
0x14000c52a  jmp     loc_14000C390
0x14000c52f  jmp     short loc_14000C555
0x14000c531  xor     esi, esi
0x14000c533  lea     r15d, [rsi+1]
0x14000c537  mov     r14, [rsp+0A8h+arg_0]
0x14000c53f  mov     edi, [rsp+0A8h+arg_18]
0x14000c546  mov     r12d, [rsp+0A8h+var_78]
0x14000c54b  mov     rax, [rsp+0A8h+var_48]
0x14000c550  mov     [rsp+0A8h+var_58], rax
0x14000c555  add     r12d, r15d
0x14000c558  jmp     loc_14000C35A
0x14000c55d  test    edi, edi
0x14000c55f  js      short loc_14000C596
0x14000c561  mov     r8d, r15d; int
0x14000c564  lea     rdx, asc_14001B440; "\r\n"
0x14000c56b  mov     rcx, r14; this
0x14000c56e  call    ?AppendString@CGenerate@@AEAAJPEBGH@Z; CGenerate::AppendString(ushort const *,int)
0x14000c573  mov     edi, eax
0x14000c575  test    eax, eax
0x14000c577  js      short loc_14000C596
0x14000c579  mov     r8d, r15d; int
0x14000c57c  lea     rdx, aText; "[text]\r\n"
0x14000c583  mov     rcx, r14; this
0x14000c586  call    ?AppendString@CGenerate@@AEAAJPEBGH@Z; CGenerate::AppendString(ushort const *,int)
0x14000c58b  mov     edi, eax
0x14000c58d  jmp     short loc_14000C596
0x14000c58f  mov     edi, [rsp+0A8h+arg_18]
0x14000c596  mov     eax, edi
0x14000c598  add     rsp, 70h
0x14000c59c  pop     r15
0x14000c59e  pop     r14
0x14000c5a0  pop     r13
0x14000c5a2  pop     r12
0x14000c5a4  pop     rdi
0x14000c5a5  pop     rsi
0x14000c5a6  pop     rbx
0x14000c5a7  retn
```
