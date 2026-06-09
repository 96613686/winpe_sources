# FSMuxMediaType::UpdateCurrentMediaTypes(CTUnkArray<FSMediaTypeArray> &,CTEntryArray<ulong> &)

- ea: `0x180063acc`
- end: `0x180063ca4`
- name: `?UpdateCurrentMediaTypes@FSMuxMediaType@@QEAAJAEAV?$CTUnkArray@VFSMediaTypeArray@@@@AEAV?$CTEntryArray@K@@@Z`
- size: `472`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x18008a0f4`

## callees

- `0x180008cf0`
- `0x180009608`
- `0x18000a880`
- `0x180063acc`
- `0x1800ea010`

## import_xrefs

- `MFPlat!MFCreateMuxStreamMediaType` at `0x180063c35`
- `MFPlat!MFCreateMuxStreamMediaType` at `0x180063c35`
- `MFPlat!MFCreateCollection` at `0x180063b36`
- `MFPlat!MFCreateCollection` at `0x180063b36`

## pseudocode

```c
__int64 __fastcall FSMuxMediaType::UpdateCurrentMediaTypes(__int64 a1, _QWORD *a2, __int64 a3)
{
  int v3; // eax
  unsigned int v7; // ebx
  __int64 v8; // rdx
  int v9; // eax
  __int64 v10; // rdx
  char v11; // bp
  __int64 i; // rsi
  __int64 v13; // r11
  unsigned int v14; // r9d
  __int64 v15; // rcx
  __int64 v16; // rdx
  __int64 v17; // rcx
  int v18; // eax
  int v19; // eax
  __int64 v21; // [rsp+60h] [rbp+8h] BYREF
  __int64 v22; // [rsp+70h] [rbp+18h] BYREF

  v3 = *(_DWORD *)(a3 + 8);
  v22 = 0;
  if ( *(_DWORD *)(a1 + 72) == v3 )
  {
    v9 = MFCreateCollection(&v22);
    v7 = v9;
    if ( v9 >= 0 )
    {
      v11 = 0;
      for ( i = 0; ; i = (unsigned int)(i + 1) )
      {
        if ( (unsigned int)i >= *(_DWORD *)(a1 + 72) )
        {
          if ( v11 )
          {
            v21 = 0;
            v19 = MFCreateMuxStreamMediaType(v22, &v21);
            v7 = v19;
            if ( v19 >= 0 )
            {
              wil::com_ptr_t<IFSClientContextInfo,wil::err_returncode_policy>::operator=((__int64 *)(a1 + 16), v21);
            }
            else if ( g_wppLevels )
            {
              WPP_SF_qD(
                *((_QWORD *)WPP_GLOBAL_Control + 2),
                89,
                WPP_6a947f3d49c93d23ab6ca77ca04b7b54_Traceguids,
                a1,
                v19);
            }
            wil::com_ptr_t<IFSSensorGroupTransform,wil::err_returncode_policy>::~com_ptr_t<IFSSensorGroupTransform,wil::err_returncode_policy>(&v21);
          }
          goto LABEL_30;
        }
        v13 = *(_QWORD *)(a1 + 80);
        v14 = *(_DWORD *)(*(_QWORD *)a3 + 4 * i);
        if ( v14 != *(_DWORD *)(v13 + 16LL * (unsigned int)i + 4) )
        {
          if ( v14 >= *(_DWORD *)(*(_QWORD *)(*a2 + 8 * i) + 24LL) )
          {
            v7 = -1072875841;
            if ( !g_wppLevels )
              goto LABEL_30;
            v8 = 87;
            goto LABEL_4;
          }
          *(_DWORD *)(v13 + 16LL * (unsigned int)i + 4) = v14;
          v11 = 1;
        }
        v15 = *(unsigned int *)(*(_QWORD *)a3 + 4 * i);
        v16 = *(_QWORD *)(*a2 + 8 * i);
        if ( (unsigned int)v15 < *(_DWORD *)(v16 + 24) )
        {
          v18 = 1;
          v17 = *(_QWORD *)(*(_QWORD *)(v16 + 16) + 8 * v15);
        }
        else
        {
          v17 = 0;
          v18 = 0;
        }
        v9 = (*(__int64 (__fastcall **)(__int64, __int64))(*(_QWORD *)v22 + 40LL))(v22, v17 & -(__int64)(v18 != 0));
        v7 = v9;
        if ( v9 < 0 )
          break;
      }
      if ( !g_wppLevels )
        goto LABEL_30;
      v10 = 88;
    }
    else
    {
      if ( !g_wppLevels )
        goto LABEL_30;
      v10 = 86;
    }
    WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), v10, WPP_6a947f3d49c93d23ab6ca77ca04b7b54_Traceguids, a1, v9);
    goto LABEL_30;
  }
  v7 = -2147024809;
  if ( g_wppLevels )
  {
    v8 = 85;
LABEL_4:
    WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), v8, WPP_6a947f3d49c93d23ab6ca77ca04b7b54_Traceguids, a1, v7);
  }
LABEL_30:
  wil::com_ptr_t<IFSSensorGroupTransform,wil::err_returncode_policy>::~com_ptr_t<IFSSensorGroupTransform,wil::err_returncode_policy>(&v22);
  return v7;
}

```

## disassembly

```asm
0x180063acc  mov     [rsp+arg_8], rbx
0x180063ad1  push    rbp
0x180063ad2  push    rsi
0x180063ad3  push    rdi
0x180063ad4  push    r14
0x180063ad6  push    r15
0x180063ad8  sub     rsp, 30h
0x180063adc  mov     eax, [r8+8]
0x180063ae0  mov     r14, r8
0x180063ae3  mov     r15, rdx
0x180063ae6  mov     rdi, rcx
0x180063ae9  mov     [rsp+58h+arg_10], 0
0x180063af2  cmp     [rcx+48h], eax
0x180063af5  jz      short loc_180063B31
0x180063af7  mov     ebx, 80070057h
0x180063afc  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180063b03  jb      loc_180063C87
0x180063b09  mov     edx, 55h ; 'U'
0x180063b0e  mov     [rsp+58h+var_38], ebx
0x180063b12  mov     rcx, cs:WPP_GLOBAL_Control
0x180063b19  lea     r8, WPP_6a947f3d49c93d23ab6ca77ca04b7b54_Traceguids
0x180063b20  mov     r9, rdi
0x180063b23  mov     rcx, [rcx+10h]
0x180063b27  call    WPP_SF_qD
0x180063b2c  jmp     loc_180063C87
0x180063b31  lea     rcx, [rsp+58h+arg_10]
0x180063b36  call    cs:__imp_MFCreateCollection
0x180063b3c  mov     ebx, eax
0x180063b3e  test    eax, eax
0x180063b40  jns     short loc_180063B5A
0x180063b42  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180063b49  jb      loc_180063C87
0x180063b4f  mov     edx, 56h ; 'V'
0x180063b54  mov     [rsp+58h+var_38], eax
0x180063b58  jmp     short loc_180063B12
0x180063b5a  xor     bpl, bpl
0x180063b5d  xor     esi, esi
0x180063b5f  cmp     esi, [rdi+48h]
0x180063b62  jnb     loc_180063C1D
0x180063b68  mov     rax, [r14]
0x180063b6b  lea     rdx, ds:0[rsi*8]
0x180063b73  mov     r11, [rdi+50h]
0x180063b77  mov     r8d, esi
0x180063b7a  add     r8, r8
0x180063b7d  mov     r9d, [rax+rsi*4]
0x180063b81  cmp     r9d, [r11+r8*8+4]
0x180063b86  jz      short loc_180063B9D
0x180063b88  mov     rax, [r15]
0x180063b8b  mov     rcx, [rax+rdx]
0x180063b8f  cmp     r9d, [rcx+18h]
0x180063b93  jnb     short loc_180063BEE
0x180063b95  mov     [r11+r8*8+4], r9d
0x180063b9a  mov     bpl, 1
0x180063b9d  mov     r9, [rsp+58h+arg_10]
0x180063ba2  mov     rax, [r9]
0x180063ba5  mov     r11, [rax+28h]
0x180063ba9  mov     rax, [r14]
0x180063bac  mov     ecx, [rax+rsi*4]
0x180063baf  mov     rax, [r15]
0x180063bb2  mov     rdx, [rax+rdx]
0x180063bb6  cmp     ecx, [rdx+18h]
0x180063bb9  jb      short loc_180063BC1
0x180063bbb  xor     ecx, ecx
0x180063bbd  xor     eax, eax
0x180063bbf  jmp     short loc_180063BCE
0x180063bc1  mov     rdx, [rdx+10h]
0x180063bc5  mov     eax, 1
0x180063bca  mov     rcx, [rdx+rcx*8]
0x180063bce  neg     eax
0x180063bd0  mov     rax, r11
0x180063bd3  sbb     rdx, rdx
0x180063bd6  and     rdx, rcx
0x180063bd9  mov     rcx, r9
0x180063bdc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180063be1  mov     ebx, eax
0x180063be3  test    eax, eax
0x180063be5  js      short loc_180063C0A
0x180063be7  inc     esi
0x180063be9  jmp     loc_180063B5F
0x180063bee  mov     ebx, 0C00D36BFh
0x180063bf3  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180063bfa  jb      loc_180063C87
0x180063c00  mov     edx, 57h ; 'W'
0x180063c05  jmp     loc_180063B0E
0x180063c0a  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180063c11  jb      short loc_180063C87
0x180063c13  mov     edx, 58h ; 'X'
0x180063c18  jmp     loc_180063B54
0x180063c1d  test    bpl, bpl
0x180063c20  jz      short loc_180063C87
0x180063c22  mov     rcx, [rsp+58h+arg_10]
0x180063c27  lea     rdx, [rsp+58h+arg_0]
0x180063c2c  mov     [rsp+58h+arg_0], 0
0x180063c35  call    cs:__imp_MFCreateMuxStreamMediaType
0x180063c3b  mov     ebx, eax
0x180063c3d  test    eax, eax
0x180063c3f  jns     short loc_180063C6F
0x180063c41  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180063c48  jb      short loc_180063C7D
0x180063c4a  mov     rcx, cs:WPP_GLOBAL_Control
0x180063c51  lea     r8, WPP_6a947f3d49c93d23ab6ca77ca04b7b54_Traceguids
0x180063c58  mov     edx, 59h ; 'Y'
0x180063c5d  mov     [rsp+58h+var_38], eax
0x180063c61  mov     r9, rdi
0x180063c64  mov     rcx, [rcx+10h]
0x180063c68  call    WPP_SF_qD
0x180063c6d  jmp     short loc_180063C7D
0x180063c6f  mov     rdx, [rsp+58h+arg_0]
0x180063c74  lea     rcx, [rdi+10h]
0x180063c78  call    ??4?$com_ptr_t@UIFSClientContextInfo@@Uerr_returncode_policy@wil@@@wil@@QEAAAEAV01@PEAUIFSClientContextInfo@@@Z; wil::com_ptr_t<IFSClientContextInfo,wil::err_returncode_policy>::operator=(IFSClientContextInfo *)
0x180063c7d  lea     rcx, [rsp+58h+arg_0]; void *
0x180063c82  call    ??1?$com_ptr_t@UIFSSensorGroupTransform@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IFSSensorGroupTransform,wil::err_returncode_policy>::~com_ptr_t<IFSSensorGroupTransform,wil::err_returncode_policy>(void)
0x180063c87  lea     rcx, [rsp+58h+arg_10]; void *
0x180063c8c  call    ??1?$com_ptr_t@UIFSSensorGroupTransform@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IFSSensorGroupTransform,wil::err_returncode_policy>::~com_ptr_t<IFSSensorGroupTransform,wil::err_returncode_policy>(void)
0x180063c91  mov     eax, ebx
0x180063c93  mov     rbx, [rsp+58h+arg_8]
0x180063c98  add     rsp, 30h
0x180063c9c  pop     r15
0x180063c9e  pop     r14
0x180063ca0  pop     rdi
0x180063ca1  pop     rsi
0x180063ca2  pop     rbp
0x180063ca3  retn
```
