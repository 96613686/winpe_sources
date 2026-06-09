# FSMCameraDeviceRegistryEntry::SetData(uchar const *,ulong)

- ea: `0x180048690`
- end: `0x1800489ea`
- name: `?SetData@FSMCameraDeviceRegistryEntry@@UEAAJPEBEK@Z`
- size: `858`
- prototype: `int(FSMCameraDeviceRegistryEntry *__hidden this, const unsigned __int8 *, unsigned int)`
- caller_count: `0`
- callee_count: `11`
- tags: `registry_config`

## callees

- `0x1800060e8`
- `0x1800060f8`
- `0x180006a98`
- `0x180006cc0`
- `0x18000d1e0`
- `0x180025608`
- `0x180048690`
- `0x180048db4`
- `0x1800490c8`
- `0x180049180`
- `0x18004bf50`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800486ae`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800486ae`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800489d1`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800489d1`

## pseudocode

```c
__int64 __fastcall FSMCameraDeviceRegistryEntry::SetData(
        FSMCameraDeviceRegistryEntry *this,
        const unsigned __int8 *a2,
        unsigned int a3)
{
  size_t v4; // rbp
  __int64 v6; // rdx
  __int64 v7; // r8
  unsigned int v8; // ebx
  int v9; // ecx
  __int64 v10; // rdx
  const void **v11; // r12
  __int64 v12; // rdx
  unsigned int v13; // eax
  size_t v14; // rdi
  unsigned int v15; // r15d
  _DWORD *v16; // rbx
  const struct std::nothrow_t *v17; // rdx
  const struct std::nothrow_t *v18; // rdx
  unsigned int *v19; // rcx
  int v20; // r9d
  unsigned __int8 Level; // al
  __int64 v22; // rdx
  void *v24; // [rsp+90h] [rbp+8h] BYREF

  v4 = a3;
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 16));
  if ( _MFControlLevel_CTRLGUID_MF_CORE_MFTS::GetLevel() >= 8u )
    WPP_SF_qdqD(*((_QWORD *)WPP_GLOBAL_Control + 27), v6, v7, this, *((_DWORD *)this + 19), a2, v4);
  if ( a2 )
  {
    if ( (_DWORD)v4 )
      goto LABEL_9;
LABEL_7:
    v8 = -2147024809;
    if ( !_MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
      goto LABEL_43;
    v10 = 22;
LABEL_42:
    WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), v10, &WPP_2c63616102ab3879fc06f5609f11f22c_Traceguids, this, v9);
    goto LABEL_43;
  }
  if ( (_DWORD)v4 )
    goto LABEL_7;
LABEL_9:
  if ( *((_BYTE *)this + 56) )
  {
    v8 = -1072875854;
    if ( _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
      WPP_SF_qD(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        23,
        &WPP_2c63616102ab3879fc06f5609f11f22c_Traceguids,
        this,
        -1072875854);
    goto LABEL_43;
  }
  if ( !a2 )
  {
    **((_DWORD **)this + 8) -= *(_DWORD *)(*((_QWORD *)this + 8) + 16LL);
    *(_DWORD *)(*((_QWORD *)this + 8) + 4LL) = 1;
    *(_DWORD *)(*((_QWORD *)this + 8) + 16LL) = 0;
    goto LABEL_32;
  }
  if ( *((_DWORD *)this + 19) == 4 )
  {
    if ( (v4 & 1) != 0 )
    {
      v8 = -2147024809;
      if ( !_MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
        goto LABEL_43;
      v10 = 24;
      goto LABEL_42;
    }
    if ( *(_WORD *)&a2[2 * ((unsigned int)v4 >> 1) - 2] )
    {
      v8 = -2147024809;
      if ( !_MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
        goto LABEL_43;
      v10 = 25;
      goto LABEL_42;
    }
  }
  v11 = (const void **)((char *)this + 64);
  v12 = *((_QWORD *)this + 8);
  v13 = *(_DWORD *)(v12 + 16);
  if ( *((_DWORD *)this + 18) < v13 )
  {
    v8 = -2147024362;
    if ( !_MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
      goto LABEL_43;
    v10 = 26;
    goto LABEL_42;
  }
  v14 = *((_DWORD *)this + 18) - v13;
  v15 = v14 + v4;
  if ( (int)v14 + (int)v4 < (unsigned int)v14 )
  {
    v8 = -2147024362;
    if ( !_MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
      goto LABEL_43;
    v10 = 27;
    goto LABEL_42;
  }
  if ( *((_DWORD *)this + 18) >= v15 )
  {
    memcpy_0((void *)(v12 + (unsigned int)v14), a2, v4);
    *(_DWORD *)*v11 = v15;
    *((_DWORD *)*v11 + 1) = *((_DWORD *)this + 19);
    *((_DWORD *)*v11 + 4) = v4;
  }
  else
  {
    wil::make_unique_nothrow<unsigned char [0]>(&v24, v15);
    v16 = v24;
    if ( !v24 )
    {
      v8 = -2147024882;
      if ( _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
        WPP_SF_qD(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          28,
          &WPP_2c63616102ab3879fc06f5609f11f22c_Traceguids,
          this,
          -2147024882);
      wistd::unique_ptr<unsigned short [0],wistd::default_delete<unsigned short [0]>>::reset(&v24, v17);
LABEL_43:
      if ( _MFControlLevel_CTRLGUID_MF_CORE_MFTS::GetLevel() )
      {
        v22 = 31;
        goto LABEL_45;
      }
      goto LABEL_46;
    }
    memcpy_0(v24, *v11, v14);
    memcpy_0((char *)v16 + v14, a2, v4);
    *v16 = v15;
    v16[1] = *((_DWORD *)this + 19);
    v16[4] = v4;
    wistd::unique_ptr<unsigned char [0],wistd::default_delete<unsigned char [0]>>::swap((char *)this + 64, &v24);
    *((_DWORD *)this + 18) = v15;
    wistd::unique_ptr<unsigned short [0],wistd::default_delete<unsigned short [0]>>::reset(&v24, v18);
  }
LABEL_32:
  if ( _MFControlLevel_CTRLGUID_MF_CORE_MFTS::GetLevel() < 0x10u )
  {
    Level = _MFControlLevel_CTRLGUID_MF_CORE_MFTS::GetLevel();
    v8 = 0;
  }
  else
  {
    v19 = (unsigned int *)*((_QWORD *)this + 8);
    v20 = *((_DWORD *)this + 19);
    if ( v19[3] )
      WPP_SF_qSSdd(
        *((_QWORD *)WPP_GLOBAL_Control + 27),
        (__int64)v19 + 2 * v19[2] + 20,
        (__int64)(v19 + 5),
        v20,
        v19[4]);
    else
      WPP_SF_qSdd(
        *((_QWORD *)WPP_GLOBAL_Control + 27),
        (_DWORD)v19 + 20,
        v19[4],
        (_DWORD)this,
        (__int64)(v19 + 5),
        v20,
        v19[4]);
    v8 = 0;
    Level = _MFControlLevel_CTRLGUID_MF_CORE_MFTS::GetLevel();
  }
  if ( Level >= 8u )
  {
    v22 = 32;
LABEL_45:
    WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 27), v22, &WPP_2c63616102ab3879fc06f5609f11f22c_Traceguids, this, v8);
  }
LABEL_46:
  LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 16));
  return v8;
}

```

## disassembly

```asm
0x180048690  push    rbx
0x180048692  push    rbp
0x180048693  push    rsi
0x180048694  push    rdi
0x180048695  push    r12
0x180048697  push    r13
0x180048699  push    r14
0x18004869b  push    r15
0x18004869d  sub     rsp, 48h
0x1800486a1  mov     rsi, rcx
0x1800486a4  mov     ebp, r8d
0x1800486a7  add     rcx, 10h; lpCriticalSection
0x1800486ab  mov     r14, rdx
0x1800486ae  call    cs:__imp_EnterCriticalSection
0x1800486b4  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_CORE_MFTS@@SAEXZ; _MFControlLevel_CTRLGUID_MF_CORE_MFTS::GetLevel(void)
0x1800486b9  cmp     al, 8
0x1800486bb  jb      short loc_1800486E3
0x1800486bd  mov     rcx, cs:WPP_GLOBAL_Control
0x1800486c4  mov     r9, rsi
0x1800486c7  mov     eax, [rsi+4Ch]
0x1800486ca  mov     dword ptr [rsp+88h+var_58], ebp
0x1800486ce  mov     [rsp+88h+var_60], r14
0x1800486d3  mov     rcx, [rcx+0D8h]
0x1800486da  mov     dword ptr [rsp+88h+var_68], eax
0x1800486de  call    WPP_SF_qdqD
0x1800486e3  xor     edi, edi
0x1800486e5  test    r14, r14
0x1800486e8  jnz     short loc_1800486F3
0x1800486ea  test    ebp, ebp
0x1800486ec  jnz     short loc_1800486F7
0x1800486ee  test    r14, r14
0x1800486f1  jz      short loc_180048715
0x1800486f3  test    ebp, ebp
0x1800486f5  jnz     short loc_180048715
0x1800486f7  mov     ecx, 80070057h
0x1800486fc  mov     ebx, ecx
0x1800486fe  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_PLATFORM@@SAEXZ; _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel(void)
0x180048703  cmp     al, 1
0x180048705  jb      loc_18004899E
0x18004870b  mov     edx, 16h
0x180048710  jmp     loc_180048980
0x180048715  cmp     [rsi+38h], dil
0x180048719  jz      short loc_18004873B
0x18004871b  mov     ebx, 0C00D36B2h
0x180048720  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_PLATFORM@@SAEXZ; _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel(void)
0x180048725  cmp     al, 1
0x180048727  jb      loc_18004899E
0x18004872d  mov     edx, 17h
0x180048732  mov     dword ptr [rsp+88h+var_68], ebx
0x180048736  jmp     loc_180048984
0x18004873b  test    r14, r14
0x18004873e  jnz     short loc_180048760
0x180048740  mov     rcx, [rsi+40h]
0x180048744  mov     eax, [rcx+10h]
0x180048747  sub     [rcx], eax
0x180048749  mov     rax, [rsi+40h]
0x18004874d  mov     dword ptr [rax+4], 1
0x180048754  mov     rax, [rsi+40h]
0x180048758  mov     [rax+10h], edi
0x18004875b  jmp     loc_1800488D6
0x180048760  cmp     dword ptr [rsi+4Ch], 4
0x180048764  jnz     short loc_1800487B5
0x180048766  test    bpl, 1
0x18004876a  jz      short loc_18004878A
0x18004876c  mov     ecx, 80070057h
0x180048771  mov     ebx, ecx
0x180048773  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_PLATFORM@@SAEXZ; _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel(void)
0x180048778  cmp     al, 1
0x18004877a  jb      loc_18004899E
0x180048780  mov     edx, 18h
0x180048785  jmp     loc_180048980
0x18004878a  mov     eax, ebp
0x18004878c  shr     eax, 1
0x18004878e  dec     eax
0x180048790  cmp     [r14+rax*2], di
0x180048795  jz      short loc_1800487B5
0x180048797  mov     ecx, 80070057h
0x18004879c  mov     ebx, ecx
0x18004879e  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_PLATFORM@@SAEXZ; _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel(void)
0x1800487a3  cmp     al, 1
0x1800487a5  jb      loc_18004899E
0x1800487ab  mov     edx, 19h
0x1800487b0  jmp     loc_180048980
0x1800487b5  lea     r12, [rsi+40h]
0x1800487b9  mov     rdx, [r12]
0x1800487bd  mov     eax, [rdx+10h]
0x1800487c0  cmp     [rsi+48h], eax
0x1800487c3  jb      loc_18004896B
0x1800487c9  mov     edi, [rsi+48h]
0x1800487cc  sub     edi, eax
0x1800487ce  lea     r15d, [rdi+rbp]
0x1800487d2  cmp     r15d, edi
0x1800487d5  jnb     short loc_1800487F5
0x1800487d7  mov     ecx, 80070216h
0x1800487dc  mov     ebx, ecx
0x1800487de  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_PLATFORM@@SAEXZ; _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel(void)
0x1800487e3  cmp     al, 1
0x1800487e5  jb      loc_18004899E
0x1800487eb  mov     edx, 1Bh
0x1800487f0  jmp     loc_180048980
0x1800487f5  cmp     [rsi+48h], r15d
0x1800487f9  jnb     loc_1800488AC
0x1800487ff  mov     edx, r15d
0x180048802  lea     rcx, [rsp+88h+arg_0]
0x18004880a  call    ??$make_unique_nothrow@$$BY0A@E@wil@@YA?AV?$unique_ptr@$$BY0A@EU?$default_delete@$$BY0A@E@wistd@@@wistd@@_K@Z; wil::make_unique_nothrow<uchar [0]>(unsigned __int64)
0x18004880f  mov     rbx, [rsp+88h+arg_0]
0x180048817  test    rbx, rbx
0x18004881a  jnz     short loc_18004885F
0x18004881c  mov     ebx, 8007000Eh
0x180048821  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_PLATFORM@@SAEXZ; _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel(void)
0x180048826  cmp     al, 1
0x180048828  jb      short loc_18004884D
0x18004882a  mov     rcx, cs:WPP_GLOBAL_Control
0x180048831  lea     r8, WPP_2c63616102ab3879fc06f5609f11f22c_Traceguids
0x180048838  mov     edx, 1Ch
0x18004883d  mov     dword ptr [rsp+88h+var_68], ebx
0x180048841  mov     r9, rsi
0x180048844  mov     rcx, [rcx+10h]
0x180048848  call    WPP_SF_qD
0x18004884d  lea     rcx, [rsp+88h+arg_0]
0x180048855  call    ?reset@?$unique_ptr@$$BY0A@GU?$default_delete@$$BY0A@G@wistd@@@wistd@@QEAAX$$T@Z; wistd::unique_ptr<ushort [0],wistd::default_delete<ushort [0]>>::reset(std::nullptr_t)
0x18004885a  jmp     loc_18004899E
0x18004885f  mov     rdx, [r12]; Src
0x180048863  mov     r8, rdi; Size
0x180048866  mov     rcx, rbx; void *
0x180048869  call    memcpy_0
0x18004886e  mov     r8, rbp; Size
0x180048871  lea     rcx, [rdi+rbx]; void *
0x180048875  mov     rdx, r14; Src
0x180048878  call    memcpy_0
0x18004887d  mov     [rbx], r15d
0x180048880  lea     rdx, [rsp+88h+arg_0]
0x180048888  mov     eax, [rsi+4Ch]
0x18004888b  mov     rcx, r12
0x18004888e  mov     [rbx+4], eax
0x180048891  mov     [rbx+10h], ebp
0x180048894  call    ?swap@?$unique_ptr@$$BY0A@EU?$default_delete@$$BY0A@E@wistd@@@wistd@@QEAAXAEAV12@@Z; wistd::unique_ptr<uchar [0],wistd::default_delete<uchar [0]>>::swap(wistd::unique_ptr<uchar [0],wistd::default_delete<uchar [0]>> &)
0x180048899  lea     rcx, [rsp+88h+arg_0]
0x1800488a1  mov     [rsi+48h], r15d
0x1800488a5  call    ?reset@?$unique_ptr@$$BY0A@GU?$default_delete@$$BY0A@G@wistd@@@wistd@@QEAAX$$T@Z; wistd::unique_ptr<ushort [0],wistd::default_delete<ushort [0]>>::reset(std::nullptr_t)
0x1800488aa  jmp     short loc_1800488D4
0x1800488ac  mov     ecx, edi
0x1800488ae  mov     r8, rbp; Size
0x1800488b1  add     rcx, rdx; void *
0x1800488b4  mov     rdx, r14; Src
0x1800488b7  call    memcpy_0
0x1800488bc  mov     rax, [r12]
0x1800488c0  mov     [rax], r15d
0x1800488c3  mov     eax, [rsi+4Ch]
0x1800488c6  mov     rcx, [r12]
0x1800488ca  mov     [rcx+4], eax
0x1800488cd  mov     rax, [r12]
0x1800488d1  mov     [rax+10h], ebp
0x1800488d4  xor     edi, edi
0x1800488d6  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_CORE_MFTS@@SAEXZ; _MFControlLevel_CTRLGUID_MF_CORE_MFTS::GetLevel(void)
0x1800488db  cmp     al, 10h
0x1800488dd  jb      short loc_180048959
0x1800488df  mov     rcx, [rsi+40h]
0x1800488e3  mov     r9d, [rsi+4Ch]
0x1800488e7  lea     rdx, [rcx+14h]
0x1800488eb  mov     r8d, [rcx+10h]
0x1800488ef  cmp     [rcx+0Ch], edi
0x1800488f2  jbe     short loc_180048932
0x1800488f4  mov     eax, [rcx+8]
0x1800488f7  mov     dword ptr [rsp+88h+var_50], r8d; char
0x1800488fc  mov     dword ptr [rsp+88h+var_58], r9d; char
0x180048901  mov     r9, rsi
0x180048904  mov     [rsp+88h+var_60], rdx; __int64
0x180048909  lea     rcx, [rcx+rax*2]
0x18004890d  add     rcx, 14h
0x180048911  mov     [rsp+88h+var_68], rcx; __int64
0x180048916  mov     rcx, cs:WPP_GLOBAL_Control
0x18004891d  mov     rcx, [rcx+0D8h]; LoggerHandle
0x180048924  call    WPP_SF_qSSdd
0x180048929  mov     ebx, edi
0x18004892b  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_CORE_MFTS@@SAEXZ; _MFControlLevel_CTRLGUID_MF_CORE_MFTS::GetLevel(void)
0x180048930  jmp     short loc_180048960
0x180048932  mov     rcx, cs:WPP_GLOBAL_Control
0x180048939  mov     dword ptr [rsp+88h+var_58], r8d
0x18004893e  mov     dword ptr [rsp+88h+var_60], r9d
0x180048943  mov     r9, rsi
0x180048946  mov     [rsp+88h+var_68], rdx
0x18004894b  mov     rcx, [rcx+0D8h]
0x180048952  call    WPP_SF_qSdd
0x180048957  jmp     short loc_180048929
0x180048959  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_CORE_MFTS@@SAEXZ; _MFControlLevel_CTRLGUID_MF_CORE_MFTS::GetLevel(void)
0x18004895e  mov     ebx, edi
0x180048960  cmp     al, 8
0x180048962  jb      short loc_1800489CD
0x180048964  mov     edx, 20h ; ' '
0x180048969  jmp     short loc_1800489AC
0x18004896b  mov     ecx, 80070216h
0x180048970  mov     ebx, ecx
0x180048972  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_PLATFORM@@SAEXZ; _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel(void)
0x180048977  cmp     al, 1
0x180048979  jb      short loc_18004899E
0x18004897b  mov     edx, 1Ah
0x180048980  mov     dword ptr [rsp+88h+var_68], ecx
0x180048984  mov     rcx, cs:WPP_GLOBAL_Control
0x18004898b  lea     r8, WPP_2c63616102ab3879fc06f5609f11f22c_Traceguids
0x180048992  mov     r9, rsi
0x180048995  mov     rcx, [rcx+10h]
0x180048999  call    WPP_SF_qD
0x18004899e  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_CORE_MFTS@@SAEXZ; _MFControlLevel_CTRLGUID_MF_CORE_MFTS::GetLevel(void)
0x1800489a3  cmp     al, 1
0x1800489a5  jb      short loc_1800489CD
0x1800489a7  mov     edx, 1Fh
0x1800489ac  mov     rcx, cs:WPP_GLOBAL_Control
0x1800489b3  lea     r8, WPP_2c63616102ab3879fc06f5609f11f22c_Traceguids
0x1800489ba  mov     r9, rsi
0x1800489bd  mov     dword ptr [rsp+88h+var_68], ebx
0x1800489c1  mov     rcx, [rcx+0D8h]
0x1800489c8  call    WPP_SF_qD
0x1800489cd  lea     rcx, [rsi+10h]; lpCriticalSection
0x1800489d1  call    cs:__imp_LeaveCriticalSection
0x1800489d7  mov     eax, ebx
0x1800489d9  add     rsp, 48h
0x1800489dd  pop     r15
0x1800489df  pop     r14
0x1800489e1  pop     r13
0x1800489e3  pop     r12
0x1800489e5  pop     rdi
0x1800489e6  pop     rsi
0x1800489e7  pop     rbp
0x1800489e8  pop     rbx
0x1800489e9  retn
```
