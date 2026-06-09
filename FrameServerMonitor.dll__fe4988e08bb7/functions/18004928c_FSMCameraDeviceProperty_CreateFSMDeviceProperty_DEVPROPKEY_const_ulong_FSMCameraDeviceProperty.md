# FSMCameraDeviceProperty::CreateFSMDeviceProperty(_DEVPROPKEY const &,ulong,FSMCameraDeviceProperty * *)

- ea: `0x18004928c`
- end: `0x1800493b6`
- name: `?CreateFSMDeviceProperty@FSMCameraDeviceProperty@@SAJAEBU_DEVPROPKEY@@KPEAPEAV1@@Z`
- size: `298`
- prototype: `__int64 __fastcall(const struct _DEVPROPKEY *, int, struct FSMCameraDeviceProperty **)`
- caller_count: `2`
- callee_count: `6`
- tags: ``

## callers

- `0x180046150`
- `0x180046490`

## callees

- `0x18000261c`
- `0x1800060e8`
- `0x1800060f8`
- `0x180006a98`
- `0x18000d4f8`
- `0x18004928c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x1800492ef`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x1800492ef`

## pseudocode

```c
__int64 __fastcall FSMCameraDeviceProperty::CreateFSMDeviceProperty(
        const struct _DEVPROPKEY *a1,
        int a2,
        struct FSMCameraDeviceProperty **a3)
{
  unsigned int v6; // edi
  int v7; // r8d
  __int64 v8; // rdx
  char *v9; // rbx
  DEVPROPID pid; // eax

  if ( a3 )
  {
    *a3 = 0;
    v9 = (char *)operator new(0x80u);
    if ( v9 )
    {
      *((_DWORD *)v9 + 2) = 1;
      *(_QWORD *)v9 = &FSMCameraDeviceProperty::`vftable';
      InitializeCriticalSection((LPCRITICAL_SECTION)(v9 + 16));
      *((_DWORD *)v9 + 15) = 0;
      *((_QWORD *)v9 + 14) = 0;
      *((_DWORD *)v9 + 30) = 0;
      if ( _MFControlLevel_CTRLGUID_MF_CORE_MFTS::GetLevel() >= 0x10u )
        WPP_SF_q(*((_QWORD *)WPP_GLOBAL_Control + 27), 13, WPP_0ce43f26f1bd3d9b7af41fd7e71dc7ae_Traceguids, v9);
      *((_OWORD *)v9 + 4) = 0;
      *((_OWORD *)v9 + 5) = 0;
      *((_OWORD *)v9 + 6) = 0;
      *((_OWORD *)v9 + 4) = a1->fmtid;
      pid = a1->pid;
      v6 = 0;
      *((_QWORD *)v9 + 10) = pid;
      *((_QWORD *)v9 + 11) = 0;
      *((_DWORD *)v9 + 24) = a2;
      *((_DWORD *)v9 + 25) = 0;
      *((_QWORD *)v9 + 13) = 0;
      *a3 = (struct FSMCameraDeviceProperty *)v9;
    }
    else
    {
      v6 = -2147024882;
      if ( _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
      {
        v8 = 11;
        goto LABEL_10;
      }
    }
  }
  else
  {
    v6 = -2147467261;
    if ( _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
    {
      v8 = (unsigned int)(v7 + 10);
LABEL_10:
      WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), v8, WPP_0ce43f26f1bd3d9b7af41fd7e71dc7ae_Traceguids, 0, v6);
    }
  }
  return v6;
}

```

## disassembly

```asm
0x18004928c  push    rbx
0x18004928e  push    rbp
0x18004928f  push    rsi
0x180049290  push    rdi
0x180049291  sub     rsp, 38h
0x180049295  mov     rsi, r8
0x180049298  mov     ebp, edx
0x18004929a  mov     rdi, rcx
0x18004929d  test    r8, r8
0x1800492a0  jnz     short loc_1800492BD
0x1800492a2  mov     edi, 80004003h
0x1800492a7  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_PLATFORM@@SAEXZ; _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel(void)
0x1800492ac  cmp     al, 1
0x1800492ae  jb      loc_1800493AB
0x1800492b4  lea     edx, [r8+0Ah]
0x1800492b8  jmp     loc_18004938D
0x1800492bd  mov     ecx, 80h; Size
0x1800492c2  mov     qword ptr [r8], 0
0x1800492c9  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800492ce  mov     rbx, rax
0x1800492d1  test    rax, rax
0x1800492d4  jz      loc_18004937A
0x1800492da  lea     rax, ??_7FSMCameraDeviceProperty@@6B@; const FSMCameraDeviceProperty::`vftable'
0x1800492e1  mov     dword ptr [rbx+8], 1
0x1800492e8  lea     rcx, [rbx+10h]; lpCriticalSection
0x1800492ec  mov     [rbx], rax
0x1800492ef  call    cs:__imp_InitializeCriticalSection
0x1800492f5  mov     dword ptr [rbx+3Ch], 0
0x1800492fc  mov     qword ptr [rbx+70h], 0
0x180049304  mov     dword ptr [rbx+78h], 0
0x18004930b  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_CORE_MFTS@@SAEXZ; _MFControlLevel_CTRLGUID_MF_CORE_MFTS::GetLevel(void)
0x180049310  cmp     al, 10h
0x180049312  jb      short loc_180049336
0x180049314  mov     rcx, cs:WPP_GLOBAL_Control
0x18004931b  lea     r8, WPP_0ce43f26f1bd3d9b7af41fd7e71dc7ae_Traceguids
0x180049322  mov     edx, 0Dh
0x180049327  mov     r9, rbx
0x18004932a  mov     rcx, [rcx+0D8h]
0x180049331  call    WPP_SF_q
0x180049336  xorps   xmm0, xmm0
0x180049339  movups  xmmword ptr [rbx+40h], xmm0
0x18004933d  movups  xmmword ptr [rbx+50h], xmm0
0x180049341  movups  xmmword ptr [rbx+60h], xmm0
0x180049345  movups  xmm0, xmmword ptr [rdi]
0x180049348  movups  xmmword ptr [rbx+40h], xmm0
0x18004934c  mov     eax, [rdi+10h]
0x18004934f  xor     edi, edi
0x180049351  mov     [rbx+50h], eax
0x180049354  mov     dword ptr [rbx+54h], 0
0x18004935b  mov     qword ptr [rbx+58h], 0
0x180049363  mov     [rbx+60h], ebp
0x180049366  mov     dword ptr [rbx+64h], 0
0x18004936d  mov     qword ptr [rbx+68h], 0
0x180049375  mov     [rsi], rbx
0x180049378  jmp     short loc_1800493AB
0x18004937a  mov     edi, 8007000Eh
0x18004937f  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_PLATFORM@@SAEXZ; _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel(void)
0x180049384  cmp     al, 1
0x180049386  jb      short loc_1800493AB
0x180049388  mov     edx, 0Bh
0x18004938d  mov     rcx, cs:WPP_GLOBAL_Control
0x180049394  lea     r8, WPP_0ce43f26f1bd3d9b7af41fd7e71dc7ae_Traceguids
0x18004939b  xor     r9d, r9d
0x18004939e  mov     [rsp+58h+var_38], edi
0x1800493a2  mov     rcx, [rcx+10h]
0x1800493a6  call    WPP_SF_qD
0x1800493ab  mov     eax, edi
0x1800493ad  add     rsp, 38h
0x1800493b1  pop     rdi
0x1800493b2  pop     rsi
0x1800493b3  pop     rbp
0x1800493b4  pop     rbx
0x1800493b5  retn
```
