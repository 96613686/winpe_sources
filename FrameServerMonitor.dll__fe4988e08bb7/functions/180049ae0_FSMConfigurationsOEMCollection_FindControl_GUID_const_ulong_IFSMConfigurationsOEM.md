# FSMConfigurationsOEMCollection::FindControl(_GUID const &,ulong,IFSMConfigurationsOEM * *)

- ea: `0x180049ae0`
- end: `0x180049c8f`
- name: `?FindControl@FSMConfigurationsOEMCollection@@UEAAJAEBU_GUID@@KPEAPEAUIFSMConfigurationsOEM@@@Z`
- size: `431`
- prototype: `__int64 __fastcall(FSMConfigurationsOEMCollection *this, const struct _GUID *, int, struct IFSMConfigurationsOEM **)`
- caller_count: `0`
- callee_count: `7`
- tags: `registry_config`

## callees

- `0x180006a98`
- `0x180011438`
- `0x180018564`
- `0x18002fa3c`
- `0x18002fd04`
- `0x180049ae0`
- `0x18004d010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180049b0a`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180049b0a`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180049c04`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180049c04`

## pseudocode

```c
__int64 __fastcall FSMConfigurationsOEMCollection::FindControl(
        FSMConfigurationsOEMCollection *this,
        const struct _GUID *a2,
        int a3,
        struct IFSMConfigurationsOEM **a4)
{
  char v5; // di
  const struct std::nothrow_t *v9; // rdx
  unsigned int v10; // ebp
  GuidTrace *v11; // rax
  const char *String; // rax
  __int64 v13; // rdi
  __int64 v14; // r15
  __int64 v15; // rcx
  _QWORD *v16; // rax
  __int64 v17; // rcx
  unsigned int v18; // edi
  __int64 v19; // rdx
  __int64 (__fastcall ***v21)(_QWORD, GUID *, struct IFSMConfigurationsOEM **); // rcx
  int v22; // eax
  _BYTE v23[104]; // [rsp+30h] [rbp-68h] BYREF

  v5 = 0;
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 8));
  v10 = *((_DWORD *)this + 16);
  if ( (unsigned __int8)byte_18005E5A5 >= 8u )
  {
    v11 = GuidTrace::GuidTrace((GuidTrace *)v23, a2);
    String = GuidTrace::GetString(v11);
    WPP_SF_qsd(
      *((_QWORD *)WPP_GLOBAL_Control + 27),
      35,
      (unsigned int)WPP_05511007120d3393f1a8ac4501dd3aa6_Traceguids,
      (_DWORD)this,
      (__int64)String,
      a3);
    v5 = 1;
  }
  if ( (v5 & 1) != 0 )
    FSString::~FSString((FSString *)v23, v9);
  if ( a4 )
    *a4 = 0;
  v13 = 0;
  if ( v10 )
  {
    while ( 1 )
    {
      v14 = (unsigned int)v13;
      v15 = *(_QWORD *)(*((_QWORD *)this + 7) + 8 * v13);
      v16 = (_QWORD *)(*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v15 + 56LL))(v15);
      if ( *v16 == *(_QWORD *)&a2->Data1 && v16[1] == *(_QWORD *)a2->Data4 )
      {
        v17 = *(_QWORD *)(*((_QWORD *)this + 7) + 8 * v13);
        if ( (*(unsigned int (__fastcall **)(__int64))(*(_QWORD *)v17 + 64LL))(v17) == a3 )
          break;
      }
      v13 = (unsigned int)(v13 + 1);
      if ( (unsigned int)v13 >= v10 )
        goto LABEL_12;
    }
    v18 = 0;
    if ( !a4
      || (v21 = *(__int64 (__fastcall ****)(_QWORD, GUID *, struct IFSMConfigurationsOEM **))(*((_QWORD *)this + 7)
                                                                                            + 8 * v14),
          v22 = (**v21)(v21, &GUID_6838cca1_e535_49cc_ae67_3fac34520215, a4),
          v18 = v22,
          v22 >= 0) )
    {
      if ( (unsigned __int8)byte_18005E5A5 < 8u )
        goto LABEL_16;
      v19 = 38;
      goto LABEL_15;
    }
    if ( g_wppLevels )
      WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), 36, WPP_05511007120d3393f1a8ac4501dd3aa6_Traceguids, this, v22);
  }
  else
  {
LABEL_12:
    v18 = -1072875819;
  }
  if ( byte_18005E5A5 )
  {
    v19 = 37;
LABEL_15:
    WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 27), v19, WPP_05511007120d3393f1a8ac4501dd3aa6_Traceguids, this, v18);
  }
LABEL_16:
  LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 8));
  return v18;
}

```

## disassembly

```asm
0x180049ae0  push    rbx
0x180049ae2  push    rbp
0x180049ae3  push    rsi
0x180049ae4  push    rdi
0x180049ae5  push    r12
0x180049ae7  push    r13
0x180049ae9  push    r14
0x180049aeb  push    r15
0x180049aed  sub     rsp, 58h
0x180049af1  mov     rsi, rcx
0x180049af4  xor     edi, edi
0x180049af6  add     rcx, 8; lpCriticalSection
0x180049afa  mov     [rsp+98h+arg_0], edi
0x180049b01  mov     r14, r9
0x180049b04  mov     r13d, r8d
0x180049b07  mov     r12, rdx
0x180049b0a  call    cs:__imp_EnterCriticalSection
0x180049b10  mov     ebp, [rsi+40h]
0x180049b13  cmp     cs:byte_18005E5A5, 8
0x180049b1a  jb      short loc_180049B60
0x180049b1c  mov     rdx, r12; struct _GUID *
0x180049b1f  lea     rcx, [rsp+98h+var_68]; this
0x180049b24  call    ??0GuidTrace@@QEAA@AEBU_GUID@@@Z; GuidTrace::GuidTrace(_GUID const &)
0x180049b29  mov     rcx, rax; this
0x180049b2c  call    ?GetString@GuidTrace@@QEBAPEBDXZ; GuidTrace::GetString(void)
0x180049b31  mov     rcx, cs:WPP_GLOBAL_Control
0x180049b38  lea     edx, [rdi+23h]
0x180049b3b  mov     [rsp+98h+var_70], r13d
0x180049b40  lea     r8, WPP_05511007120d3393f1a8ac4501dd3aa6_Traceguids
0x180049b47  mov     r9, rsi
0x180049b4a  mov     [rsp+98h+var_78], rax
0x180049b4f  mov     rcx, [rcx+0D8h]
0x180049b56  call    WPP_SF_qsd
0x180049b5b  mov     edi, 1
0x180049b60  test    dil, 1
0x180049b64  jz      short loc_180049B70
0x180049b66  lea     rcx, [rsp+98h+var_68]; this
0x180049b6b  call    ??1FSString@@QEAA@XZ; FSString::~FSString(void)
0x180049b70  test    r14, r14
0x180049b73  jz      short loc_180049B7C
0x180049b75  mov     qword ptr [r14], 0
0x180049b7c  xor     edi, edi
0x180049b7e  test    ebp, ebp
0x180049b80  jz      short loc_180049BCC
0x180049b82  mov     rax, [rsi+38h]
0x180049b86  mov     r15d, edi
0x180049b89  mov     rcx, [rax+rdi*8]
0x180049b8d  mov     rax, [rcx]
0x180049b90  mov     rax, [rax+38h]
0x180049b94  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180049b99  mov     rcx, [rax]
0x180049b9c  cmp     rcx, [r12]
0x180049ba0  jnz     short loc_180049BC6
0x180049ba2  mov     rax, [rax+8]
0x180049ba6  cmp     rax, [r12+8]
0x180049bab  jnz     short loc_180049BC6
0x180049bad  mov     rax, [rsi+38h]
0x180049bb1  mov     rcx, [rax+rdi*8]
0x180049bb5  mov     rax, [rcx]
0x180049bb8  mov     rax, [rax+40h]
0x180049bbc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180049bc1  cmp     eax, r13d
0x180049bc4  jz      short loc_180049C1D
0x180049bc6  inc     edi
0x180049bc8  cmp     edi, ebp
0x180049bca  jb      short loc_180049B82
0x180049bcc  mov     edi, 0C00D36D5h
0x180049bd1  cmp     cs:byte_18005E5A5, 1
0x180049bd8  jb      short loc_180049C00
0x180049bda  mov     edx, 25h ; '%'
0x180049bdf  mov     rcx, cs:WPP_GLOBAL_Control
0x180049be6  lea     r8, WPP_05511007120d3393f1a8ac4501dd3aa6_Traceguids
0x180049bed  mov     r9, rsi
0x180049bf0  mov     dword ptr [rsp+98h+var_78], edi
0x180049bf4  mov     rcx, [rcx+0D8h]
0x180049bfb  call    WPP_SF_qD
0x180049c00  lea     rcx, [rsi+8]; lpCriticalSection
0x180049c04  call    cs:__imp_LeaveCriticalSection
0x180049c0a  mov     eax, edi
0x180049c0c  add     rsp, 58h
0x180049c10  pop     r15
0x180049c12  pop     r14
0x180049c14  pop     r13
0x180049c16  pop     r12
0x180049c18  pop     rdi
0x180049c19  pop     rsi
0x180049c1a  pop     rbp
0x180049c1b  pop     rbx
0x180049c1c  retn
0x180049c1d  xor     edi, edi
0x180049c1f  test    r14, r14
0x180049c22  jz      short loc_180049C78
0x180049c24  mov     rax, [rsi+38h]
0x180049c28  lea     rdx, _GUID_6838cca1_e535_49cc_ae67_3fac34520215
0x180049c2f  mov     r8, r14
0x180049c32  mov     rcx, [rax+r15*8]
0x180049c36  mov     rax, [rcx]
0x180049c39  mov     rax, [rax]
0x180049c3c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180049c41  mov     edi, eax
0x180049c43  test    eax, eax
0x180049c45  jns     short loc_180049C78
0x180049c47  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180049c4e  jb      short loc_180049BD1
0x180049c50  mov     rcx, cs:WPP_GLOBAL_Control
0x180049c57  lea     r8, WPP_05511007120d3393f1a8ac4501dd3aa6_Traceguids
0x180049c5e  mov     edx, 24h ; '$'
0x180049c63  mov     dword ptr [rsp+98h+var_78], eax
0x180049c67  mov     r9, rsi
0x180049c6a  mov     rcx, [rcx+10h]
0x180049c6e  call    WPP_SF_qD
0x180049c73  jmp     loc_180049BD1
0x180049c78  cmp     cs:byte_18005E5A5, 8
0x180049c7f  jb      loc_180049C00
0x180049c85  mov     edx, 26h ; '&'
0x180049c8a  jmp     loc_180049BDF
```
