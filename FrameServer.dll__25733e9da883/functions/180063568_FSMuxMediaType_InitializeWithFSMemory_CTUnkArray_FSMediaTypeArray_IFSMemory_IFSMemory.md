# FSMuxMediaType::InitializeWithFSMemory(CTUnkArray<FSMediaTypeArray> &,IFSMemory *,IFSMemory *)

- ea: `0x180063568`
- end: `0x1800637c7`
- name: `?InitializeWithFSMemory@FSMuxMediaType@@QEAAJAEAV?$CTUnkArray@VFSMediaTypeArray@@@@PEAUIFSMemory@@1@Z`
- size: `607`
- prototype: `__int64 __fastcall(__int64, _QWORD *, __int64, __int64)`
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18008c54c`

## callees

- `0x180008cf0`
- `0x180009608`
- `0x18000a880`
- `0x18006256c`
- `0x1800625dc`
- `0x180063568`
- `0x1800ea010`

## import_xrefs

- `MFPlat!MFCreateMuxStreamMediaType` at `0x1800636ed`
- `MFPlat!MFCreateMuxStreamMediaType` at `0x1800636ed`
- `MFPlat!MFCreateCollection` at `0x180063630`
- `MFPlat!MFCreateCollection` at `0x180063630`

## pseudocode

```c
__int64 __fastcall FSMuxMediaType::InitializeWithFSMemory(__int64 a1, _QWORD *a2, __int64 a3, __int64 a4)
{
  unsigned int v7; // ebx
  int v8; // eax
  __int64 v9; // rdx
  __int64 i; // rsi
  unsigned int v11; // edx
  __int64 v12; // r9
  __int64 j; // rsi
  __int64 v15; // [rsp+30h] [rbp-10h] BYREF
  __int64 v16; // [rsp+38h] [rbp-8h] BYREF
  __int64 v17; // [rsp+70h] [rbp+30h] BYREF

  v16 = 0;
  v17 = 0;
  v15 = 0;
  if ( a3 )
  {
    v8 = FSTMemory<MuxStreamCurrentMediaType>::AttachFSMemory(a1 + 64, a3);
    v7 = v8;
    if ( v8 >= 0 )
    {
      v8 = FSTMemory<unsigned __int64>::AttachFSMemory(a1 + 24, a4);
      v7 = v8;
      if ( v8 >= 0 )
      {
        v8 = MFCreateCollection(&v17);
        v7 = v8;
        if ( v8 >= 0 )
        {
          for ( i = 0; (unsigned int)i < *(_DWORD *)(a1 + 72); i = (unsigned int)(i + 1) )
          {
            v11 = *(_DWORD *)(*(_QWORD *)(a1 + 80) + 16LL * (unsigned int)i + 4);
            if ( v11 == -1 || (v12 = *(_QWORD *)(*a2 + 8 * i), v11 >= *(_DWORD *)(v12 + 24)) )
            {
              v8 = (*(__int64 (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v17 + 40LL))(v17, 0);
              v7 = v8;
              if ( v8 < 0 )
              {
                if ( !g_wppLevels )
                  goto LABEL_39;
                v9 = 77;
                goto LABEL_8;
              }
            }
            else
            {
              v8 = (*(__int64 (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v17 + 40LL))(
                     v17,
                     *(_QWORD *)(*(_QWORD *)(v12 + 16) + 8LL * v11));
              v7 = v8;
              if ( v8 < 0 )
              {
                if ( !g_wppLevels )
                  goto LABEL_39;
                v9 = 76;
                goto LABEL_8;
              }
            }
          }
          v8 = MFCreateMuxStreamMediaType(v17, &v15);
          v7 = v8;
          if ( v8 >= 0 )
          {
            v8 = (*(__int64 (__fastcall **)(__int64, __int64 *, GUID *, __int64 *))(*(_QWORD *)v15 + 136LL))(
                   v15,
                   MF_MEDIATYPE_MULTIPLEXED_MANAGER,
                   &GUID_505a2c72_42f7_4690_aeab_8f513d0ffdb8,
                   &v16);
            v7 = v8;
            if ( v8 >= 0 )
            {
              for ( j = 0; ; j = (unsigned int)(j + 1) )
              {
                if ( (unsigned int)j >= *(_DWORD *)(a1 + 32) )
                {
                  wil::com_ptr_t<IFSClientContextInfo,wil::err_returncode_policy>::operator=(a1 + 16, v15);
                  goto LABEL_39;
                }
                v8 = (*(__int64 (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v16 + 48LL))(
                       v16,
                       *(_QWORD *)(*(_QWORD *)(a1 + 40) + 8 * j));
                v7 = v8;
                if ( v8 < 0 )
                  break;
              }
              if ( !g_wppLevels )
                goto LABEL_39;
              v9 = 80;
            }
            else
            {
              if ( !g_wppLevels )
                goto LABEL_39;
              v9 = 79;
            }
          }
          else
          {
            if ( !g_wppLevels )
              goto LABEL_39;
            v9 = 78;
          }
        }
        else
        {
          if ( !g_wppLevels )
            goto LABEL_39;
          v9 = 75;
        }
      }
      else
      {
        if ( !g_wppLevels )
          goto LABEL_39;
        v9 = 74;
      }
    }
    else
    {
      if ( !g_wppLevels )
        goto LABEL_39;
      v9 = 73;
    }
LABEL_8:
    WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), v9, WPP_6a947f3d49c93d23ab6ca77ca04b7b54_Traceguids, a1, v8);
    goto LABEL_39;
  }
  v7 = -2147024809;
  if ( g_wppLevels )
    WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), 72, WPP_6a947f3d49c93d23ab6ca77ca04b7b54_Traceguids, a1, -2147024809);
LABEL_39:
  wil::com_ptr_t<IFSSensorGroupTransform,wil::err_returncode_policy>::~com_ptr_t<IFSSensorGroupTransform,wil::err_returncode_policy>(&v15);
  wil::com_ptr_t<IFSSensorGroupTransform,wil::err_returncode_policy>::~com_ptr_t<IFSSensorGroupTransform,wil::err_returncode_policy>(&v17);
  wil::com_ptr_t<IFSSensorGroupTransform,wil::err_returncode_policy>::~com_ptr_t<IFSSensorGroupTransform,wil::err_returncode_policy>(&v16);
  return v7;
}

```

## disassembly

```asm
0x180063568  mov     [rsp-18h+arg_0], rbx
0x18006356d  mov     [rsp-18h+arg_8], rsi
0x180063572  push    rbp
0x180063573  push    rdi
0x180063574  push    r14
0x180063576  mov     rbp, rsp
0x180063579  sub     rsp, 40h
0x18006357d  mov     [rbp+var_8], 0
0x180063585  mov     rsi, r9
0x180063588  mov     [rbp+arg_10], 0
0x180063590  mov     r14, rdx
0x180063593  mov     [rbp+var_10], 0
0x18006359b  mov     rdi, rcx
0x18006359e  test    r8, r8
0x1800635a1  jnz     short loc_1800635DC
0x1800635a3  mov     ebx, 80070057h
0x1800635a8  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1800635af  jb      loc_180063797
0x1800635b5  lea     edx, [r8+48h]
0x1800635b9  mov     [rsp+40h+var_20], ebx
0x1800635bd  mov     rcx, cs:WPP_GLOBAL_Control
0x1800635c4  lea     r8, WPP_6a947f3d49c93d23ab6ca77ca04b7b54_Traceguids
0x1800635cb  mov     r9, rdi
0x1800635ce  mov     rcx, [rcx+10h]
0x1800635d2  call    WPP_SF_qD
0x1800635d7  jmp     loc_180063797
0x1800635dc  add     rcx, 40h ; '@'
0x1800635e0  mov     rdx, r8
0x1800635e3  call    ?AttachFSMemory@?$FSTMemory@UMuxStreamCurrentMediaType@@@@QEAAJPEAUIFSMemory@@@Z; FSTMemory<MuxStreamCurrentMediaType>::AttachFSMemory(IFSMemory *)
0x1800635e8  mov     ebx, eax
0x1800635ea  test    eax, eax
0x1800635ec  jns     short loc_180063606
0x1800635ee  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1800635f5  jb      loc_180063797
0x1800635fb  mov     edx, 49h ; 'I'
0x180063600  mov     [rsp+40h+var_20], eax
0x180063604  jmp     short loc_1800635BD
0x180063606  lea     rcx, [rdi+18h]
0x18006360a  mov     rdx, rsi
0x18006360d  call    ?AttachFSMemory@?$FSTMemory@_K@@QEAAJPEAUIFSMemory@@@Z; FSTMemory<unsigned __int64>::AttachFSMemory(IFSMemory *)
0x180063612  mov     ebx, eax
0x180063614  test    eax, eax
0x180063616  jns     short loc_18006362C
0x180063618  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18006361f  jb      loc_180063797
0x180063625  mov     edx, 4Ah ; 'J'
0x18006362a  jmp     short loc_180063600
0x18006362c  lea     rcx, [rbp+arg_10]
0x180063630  call    cs:__imp_MFCreateCollection
0x180063636  mov     ebx, eax
0x180063638  test    eax, eax
0x18006363a  jns     short loc_180063650
0x18006363c  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180063643  jb      loc_180063797
0x180063649  mov     edx, 4Bh ; 'K'
0x18006364e  jmp     short loc_180063600
0x180063650  xor     esi, esi
0x180063652  cmp     esi, [rdi+48h]
0x180063655  jnb     loc_1800636E5
0x18006365b  mov     rax, [rdi+50h]
0x18006365f  mov     ecx, esi
0x180063661  add     rcx, rcx
0x180063664  mov     edx, [rax+rcx*8+4]
0x180063668  cmp     edx, 0FFFFFFFFh
0x18006366b  jz      short loc_1800636B2
0x18006366d  mov     rax, [r14]
0x180063670  mov     r9, [rax+rsi*8]
0x180063674  cmp     edx, [r9+18h]
0x180063678  jnb     short loc_1800636B2
0x18006367a  mov     rcx, [rbp+arg_10]
0x18006367e  mov     r8d, edx
0x180063681  mov     rdx, [r9+10h]
0x180063685  mov     rax, [rcx]
0x180063688  mov     rdx, [rdx+r8*8]
0x18006368c  mov     rax, [rax+28h]
0x180063690  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180063695  mov     ebx, eax
0x180063697  test    eax, eax
0x180063699  jns     short loc_1800636CA
0x18006369b  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1800636a2  jb      loc_180063797
0x1800636a8  mov     edx, 4Ch ; 'L'
0x1800636ad  jmp     loc_180063600
0x1800636b2  mov     rcx, [rbp+arg_10]
0x1800636b6  xor     edx, edx
0x1800636b8  mov     rax, [rcx]
0x1800636bb  mov     rax, [rax+28h]
0x1800636bf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800636c4  mov     ebx, eax
0x1800636c6  test    eax, eax
0x1800636c8  js      short loc_1800636CE
0x1800636ca  inc     esi
0x1800636cc  jmp     short loc_180063652
0x1800636ce  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1800636d5  jb      loc_180063797
0x1800636db  mov     edx, 4Dh ; 'M'
0x1800636e0  jmp     loc_180063600
0x1800636e5  mov     rcx, [rbp+arg_10]
0x1800636e9  lea     rdx, [rbp+var_10]
0x1800636ed  call    cs:__imp_MFCreateMuxStreamMediaType
0x1800636f3  mov     ebx, eax
0x1800636f5  test    eax, eax
0x1800636f7  jns     short loc_180063710
0x1800636f9  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180063700  jb      loc_180063797
0x180063706  mov     edx, 4Eh ; 'N'
0x18006370b  jmp     loc_180063600
0x180063710  mov     rcx, [rbp+var_10]
0x180063714  lea     r9, [rbp+var_8]
0x180063718  lea     r8, _GUID_505a2c72_42f7_4690_aeab_8f513d0ffdb8
0x18006371f  lea     rdx, MF_MEDIATYPE_MULTIPLEXED_MANAGER
0x180063726  mov     rax, [rcx]
0x180063729  mov     rax, [rax+88h]
0x180063730  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180063735  mov     ebx, eax
0x180063737  test    eax, eax
0x180063739  jns     short loc_18006374E
0x18006373b  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180063742  jb      short loc_180063797
0x180063744  mov     edx, 4Fh ; 'O'
0x180063749  jmp     loc_180063600
0x18006374e  xor     esi, esi
0x180063750  cmp     esi, [rdi+20h]
0x180063753  jnb     short loc_18006378A
0x180063755  mov     rcx, [rbp+var_8]
0x180063759  mov     rdx, [rdi+28h]
0x18006375d  mov     rax, [rcx]
0x180063760  mov     rdx, [rdx+rsi*8]
0x180063764  mov     rax, [rax+30h]
0x180063768  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006376d  mov     ebx, eax
0x18006376f  test    eax, eax
0x180063771  js      short loc_180063777
0x180063773  inc     esi
0x180063775  jmp     short loc_180063750
0x180063777  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18006377e  jb      short loc_180063797
0x180063780  mov     edx, 50h ; 'P'
0x180063785  jmp     loc_180063600
0x18006378a  mov     rdx, [rbp+var_10]
0x18006378e  lea     rcx, [rdi+10h]
0x180063792  call    ??4?$com_ptr_t@UIFSClientContextInfo@@Uerr_returncode_policy@wil@@@wil@@QEAAAEAV01@PEAUIFSClientContextInfo@@@Z; wil::com_ptr_t<IFSClientContextInfo,wil::err_returncode_policy>::operator=(IFSClientContextInfo *)
0x180063797  lea     rcx, [rbp+var_10]; void *
0x18006379b  call    ??1?$com_ptr_t@UIFSSensorGroupTransform@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IFSSensorGroupTransform,wil::err_returncode_policy>::~com_ptr_t<IFSSensorGroupTransform,wil::err_returncode_policy>(void)
0x1800637a0  lea     rcx, [rbp+arg_10]; void *
0x1800637a4  call    ??1?$com_ptr_t@UIFSSensorGroupTransform@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IFSSensorGroupTransform,wil::err_returncode_policy>::~com_ptr_t<IFSSensorGroupTransform,wil::err_returncode_policy>(void)
0x1800637a9  lea     rcx, [rbp+var_8]; void *
0x1800637ad  call    ??1?$com_ptr_t@UIFSSensorGroupTransform@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IFSSensorGroupTransform,wil::err_returncode_policy>::~com_ptr_t<IFSSensorGroupTransform,wil::err_returncode_policy>(void)
0x1800637b2  mov     rsi, [rsp+40h+arg_8]
0x1800637b7  mov     eax, ebx
0x1800637b9  mov     rbx, [rsp+40h+arg_0]
0x1800637be  add     rsp, 40h
0x1800637c2  pop     r14
0x1800637c4  pop     rdi
0x1800637c5  pop     rbp
0x1800637c6  retn
```
