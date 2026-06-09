# CTieredVolume::GetFileTieringStateForPinnedFile(TE_FILE_ID_128 *,_STORAGE_TIER_CLASS,__MIDL___MIDL_itf_tieringengine_0000_0000_0002 *,__MIDL___MIDL_itf_tieringengine_0000_0000_0003 *)

- ea: `0x14003cde0`
- end: `0x14003cfad`
- name: `?GetFileTieringStateForPinnedFile@CTieredVolume@@AEAAJPEAUTE_FILE_ID_128@@W4_STORAGE_TIER_CLASS@@PEAW4__MIDL___MIDL_itf_tieringengine_0000_0000_0002@@PEAW4__MIDL___MIDL_itf_tieringengine_0000_0000_0003@@@Z`
- size: `461`
- prototype: `__int64 __fastcall(CTieredVolume *this, struct TE_FILE_ID_128 *, enum _STORAGE_TIER_CLASS, enum __MIDL___MIDL_itf_tieringengine_0000_0000_0002 *, enum __MIDL___MIDL_itf_tieringengine_0000_0000_0003 *)`
- caller_count: `1`
- callee_count: `7`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x14003cfb4`

## callees

- `0x140004aa8`
- `0x14000ccc0`
- `0x14000f5fc`
- `0x1400127dc`
- `0x1400185a0`
- `0x14003ca54`
- `0x14003cde0`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x14003cf24`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x14003cf24`

## pseudocode

```c
__int64 __fastcall CTieredVolume::GetFileTieringStateForPinnedFile(
        CTieredVolume *this,
        struct TE_FILE_ID_128 *a2,
        enum _STORAGE_TIER_CLASS a3,
        enum __MIDL___MIDL_itf_tieringengine_0000_0000_0002 *a4,
        enum __MIDL___MIDL_itf_tieringengine_0000_0000_0003 *a5)
{
  int v8; // eax
  unsigned int v9; // ebx
  unsigned __int16 *v11; // r9
  int FilePlacementByTier_ApiHandler; // r13d
  void *v13; // rbx
  enum _STORAGE_TIER_CLASS v14; // ebp
  int v15; // r14d
  int v16; // r15d
  const struct _GUID *v17; // r12
  enum __MIDL___MIDL_itf_tieringengine_0000_0000_0003 *v18; // rax
  enum _STORAGE_TIER_CLASS v19; // [rsp+40h] [rbp-58h] BYREF
  LPVOID pv; // [rsp+48h] [rbp-50h] BYREF

  pv = 0;
  v19 = StorageTierClassUnspecified;
  v8 = CTieredVolume::ReferenceVolume(this, 0);
  v9 = v8;
  if ( v8 >= 0 )
  {
    FilePlacementByTier_ApiHandler = CTieredVolume::GetFilePlacementByTier_ApiHandler(
                                       this,
                                       a2,
                                       (int *)&v19,
                                       (struct _GUID **)&pv);
    if ( FilePlacementByTier_ApiHandler < 0 || (v13 = pv) == 0 )
    {
      *(_DWORD *)a4 = 0;
      *(_DWORD *)a5 = 0;
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_iiZd(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          97,
          (unsigned int)&WPP_db0c4653e1f131e4f6800413feb2b973_Traceguids,
          *((_QWORD *)a2 + 1),
          *(_QWORD *)a2,
          (__int64)this + 672,
          FilePlacementByTier_ApiHandler);
      }
      goto LABEL_26;
    }
    v14 = v19;
    v15 = 0;
    v16 = 0;
    v17 = (const struct _GUID *)pv;
    if ( v19 <= StorageTierClassUnspecified )
      goto LABEL_19;
    do
    {
      v19 = StorageTierClassUnspecified;
      CTieredVolume::GetTierInfo((RTL_SRWLOCK *)this, v17, &v19, v11);
      if ( *(_QWORD *)&v17[1].Data1 )
      {
        if ( v19 == a3 )
          ++v15;
        else
          ++v16;
      }
      v17 = (const struct _GUID *)((char *)v17 + 24);
      --v14;
    }
    while ( v14 > StorageTierClassUnspecified );
    v13 = pv;
    if ( v15 )
    {
      v18 = a5;
      if ( !v16 )
      {
        *(_DWORD *)a4 = 1;
        *(_DWORD *)a5 = 1;
LABEL_21:
        CoTaskMemFree(v13);
LABEL_26:
        CTieredVolume::DereferenceVolume((RTL_SRWLOCK *)this);
        return (unsigned int)FilePlacementByTier_ApiHandler;
      }
      *(_DWORD *)a4 = 2;
    }
    else
    {
LABEL_19:
      v18 = a5;
      *(_DWORD *)a4 = 3;
    }
    *(_DWORD *)v18 = 4;
    goto LABEL_21;
  }
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    WPP_SF_Dd(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      96,
      &WPP_db0c4653e1f131e4f6800413feb2b973_Traceguids,
      *((unsigned int *)this + 32),
      v8);
  }
  return v9;
}

```

## disassembly

```asm
0x14003cde0  mov     [rsp+arg_10], r8d
0x14003cde5  push    rbx
0x14003cde6  push    rbp
0x14003cde7  push    rsi
0x14003cde8  push    rdi
0x14003cde9  push    r12
0x14003cdeb  push    r13
0x14003cded  push    r14
0x14003cdef  push    r15
0x14003cdf1  sub     rsp, 58h
0x14003cdf5  mov     r14, rdx
0x14003cdf8  mov     [rsp+98h+pv], 0
0x14003ce01  xor     edx, edx; bool
0x14003ce03  mov     [rsp+98h+var_58], 0
0x14003ce0b  mov     rdi, r9
0x14003ce0e  mov     rsi, rcx
0x14003ce11  call    ?ReferenceVolume@CTieredVolume@@QEAAJ_N@Z; CTieredVolume::ReferenceVolume(bool)
0x14003ce16  mov     ebx, eax
0x14003ce18  test    eax, eax
0x14003ce1a  jns     short loc_14003CE62
0x14003ce1c  mov     rcx, cs:WPP_GLOBAL_Control
0x14003ce23  lea     rdx, WPP_GLOBAL_Control
0x14003ce2a  cmp     rcx, rdx
0x14003ce2d  jz      short loc_14003CE5B
0x14003ce2f  test    byte ptr [rcx+1Ch], 1
0x14003ce33  jz      short loc_14003CE5B
0x14003ce35  cmp     byte ptr [rcx+19h], 2
0x14003ce39  jb      short loc_14003CE5B
0x14003ce3b  mov     r9d, [rsi+80h]
0x14003ce42  lea     r8, WPP_db0c4653e1f131e4f6800413feb2b973_Traceguids
0x14003ce49  mov     rcx, [rcx+10h]
0x14003ce4d  mov     edx, 60h ; '`'
0x14003ce52  mov     dword ptr [rsp+98h+var_78], eax
0x14003ce56  call    WPP_SF_Dd
0x14003ce5b  mov     eax, ebx
0x14003ce5d  jmp     loc_14003CF9C
0x14003ce62  lea     r9, [rsp+98h+pv]; struct __MIDL___MIDL_itf_tieringengine_0000_0000_0008 **
0x14003ce67  mov     rdx, r14; struct TE_FILE_ID_128 *
0x14003ce6a  lea     r8, [rsp+98h+var_58]; int *
0x14003ce6f  mov     rcx, rsi; this
0x14003ce72  call    ?GetFilePlacementByTier_ApiHandler@CTieredVolume@@QEAAJPEAUTE_FILE_ID_128@@PEAJPEAPEAU__MIDL___MIDL_itf_tieringengine_0000_0000_0008@@@Z; CTieredVolume::GetFilePlacementByTier_ApiHandler(TE_FILE_ID_128 *,long *,__MIDL___MIDL_itf_tieringengine_0000_0000_0008 * *)
0x14003ce77  mov     r13d, eax
0x14003ce7a  test    eax, eax
0x14003ce7c  js      loc_14003CF2C
0x14003ce82  mov     rbx, [rsp+98h+pv]
0x14003ce87  test    rbx, rbx
0x14003ce8a  jz      loc_14003CF2C
0x14003ce90  mov     ebp, [rsp+98h+var_58]
0x14003ce94  xor     r14d, r14d
0x14003ce97  xor     r15d, r15d
0x14003ce9a  mov     r12, rbx
0x14003ce9d  test    ebp, ebp
0x14003ce9f  jle     short loc_14003CF0D
0x14003cea1  mov     ebx, [rsp+98h+arg_10]
0x14003cea8  lea     r8, [rsp+98h+var_58]; enum _STORAGE_TIER_CLASS *
0x14003cead  mov     [rsp+98h+var_58], 0
0x14003ceb5  mov     rdx, r12; struct _GUID *
0x14003ceb8  mov     rcx, rsi; this
0x14003cebb  call    ?GetTierInfo@CTieredVolume@@QEAAJPEBU_GUID@@PEAW4_STORAGE_TIER_CLASS@@PEAG@Z; CTieredVolume::GetTierInfo(_GUID const *,_STORAGE_TIER_CLASS *,ushort *)
0x14003cec0  cmp     qword ptr [r12+10h], 0
0x14003cec6  jbe     short loc_14003CED6
0x14003cec8  cmp     [rsp+98h+var_58], ebx
0x14003cecc  jnz     short loc_14003CED3
0x14003cece  inc     r14d
0x14003ced1  jmp     short loc_14003CED6
0x14003ced3  inc     r15d
0x14003ced6  add     r12, 18h
0x14003ceda  dec     ebp
0x14003cedc  test    ebp, ebp
0x14003cede  jg      short loc_14003CEA8
0x14003cee0  mov     rbx, [rsp+98h+pv]
0x14003cee5  test    r14d, r14d
0x14003cee8  jz      short loc_14003CF0D
0x14003ceea  mov     rax, [rsp+98h+arg_20]
0x14003cef2  test    r15d, r15d
0x14003cef5  jnz     short loc_14003CF05
0x14003cef7  mov     dword ptr [rdi], 1
0x14003cefd  mov     dword ptr [rax], 1
0x14003cf03  jmp     short loc_14003CF21
0x14003cf05  mov     dword ptr [rdi], 2
0x14003cf0b  jmp     short loc_14003CF1B
0x14003cf0d  mov     rax, [rsp+98h+arg_20]
0x14003cf15  mov     dword ptr [rdi], 3
0x14003cf1b  mov     dword ptr [rax], 4
0x14003cf21  mov     rcx, rbx; pv
0x14003cf24  call    cs:__imp_CoTaskMemFree
0x14003cf2a  jmp     short loc_14003CF91
0x14003cf2c  mov     rax, [rsp+98h+arg_20]
0x14003cf34  mov     dword ptr [rdi], 0
0x14003cf3a  mov     dword ptr [rax], 0
0x14003cf40  mov     rcx, cs:WPP_GLOBAL_Control
0x14003cf47  lea     rdx, WPP_GLOBAL_Control
0x14003cf4e  cmp     rcx, rdx
0x14003cf51  jz      short loc_14003CF91
0x14003cf53  test    byte ptr [rcx+1Ch], 1
0x14003cf57  jz      short loc_14003CF91
0x14003cf59  cmp     byte ptr [rcx+19h], 2
0x14003cf5d  jb      short loc_14003CF91
0x14003cf5f  mov     r9, [r14+8]
0x14003cf63  lea     rax, [rsi+2A0h]
0x14003cf6a  mov     rcx, [rcx+10h]
0x14003cf6e  lea     r8, WPP_db0c4653e1f131e4f6800413feb2b973_Traceguids
0x14003cf75  mov     [rsp+98h+var_68], r13d
0x14003cf7a  mov     edx, 61h ; 'a'
0x14003cf7f  mov     [rsp+98h+var_70], rax
0x14003cf84  mov     rax, [r14]
0x14003cf87  mov     [rsp+98h+var_78], rax
0x14003cf8c  call    WPP_SF_iiZd
0x14003cf91  mov     rcx, rsi; this
0x14003cf94  call    ?DereferenceVolume@CTieredVolume@@QEAAXXZ; CTieredVolume::DereferenceVolume(void)
0x14003cf99  mov     eax, r13d
0x14003cf9c  add     rsp, 58h
0x14003cfa0  pop     r15
0x14003cfa2  pop     r14
0x14003cfa4  pop     r13
0x14003cfa6  pop     r12
0x14003cfa8  pop     rdi
0x14003cfa9  pop     rsi
0x14003cfaa  pop     rbp
0x14003cfab  pop     rbx
0x14003cfac  retn
```
