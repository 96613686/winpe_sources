# SensorGroup::CreateMediaSource(IMFMediaSource * *)

- ea: `0x180032200`
- end: `0x1800324fa`
- name: `?CreateMediaSource@SensorGroup@@UEAAJPEAPEAUIMFMediaSource@@@Z`
- size: `762`
- prototype: `__int64 __fastcall(SensorGroup *this, struct IMFMediaSource **)`
- caller_count: `0`
- callee_count: `3`
- tags: `reparse_path`

## callees

- `0x180005fa0`
- `0x180032200`
- `0x180077010`

## import_xrefs

- `MFPlat!MFCreateAttributes` at `0x18003236b`
- `MFPlat!MFCreateAttributes` at `0x18003236b`
- `MFCORE!MFCreateDeviceSource` at `0x180032474`
- `MFCORE!MFCreateDeviceSource` at `0x180032474`

## pseudocode

```c
__int64 __fastcall SensorGroup::CreateMediaSource(SensorGroup *this, struct IMFMediaSource **a2)
{
  IMFAttributes *v4; // rcx
  __int64 (__fastcall ***v5)(_QWORD, GUID *, __int64 *); // r9
  HRESULT v6; // eax
  unsigned int v7; // ebx
  __int64 v8; // rdx
  __int64 v9; // rcx
  __int64 (__fastcall **v10)(SensorGroup *, GUID *, __int64 *); // rax
  __int64 v11; // rcx
  __int64 v13; // [rsp+30h] [rbp-10h] BYREF
  __int64 v14; // [rsp+38h] [rbp-8h] BYREF
  UINT32 cInitialSize; // [rsp+60h] [rbp+20h] BYREF
  IMFAttributes *ppMFAttributes; // [rsp+70h] [rbp+30h] BYREF
  __int64 v17; // [rsp+78h] [rbp+38h] BYREF

  v4 = 0;
  ppMFAttributes = 0;
  v14 = 0;
  v5 = (__int64 (__fastcall ***)(_QWORD, GUID *, __int64 *))*((_QWORD *)this + 22);
  cInitialSize = 0;
  v17 = 0;
  v13 = 0;
  if ( !v5 )
  {
    v6 = -1072875850;
    v7 = -1072875850;
    if ( !g_wppLevels )
      goto LABEL_45;
    v8 = 41;
    goto LABEL_39;
  }
  v6 = (**v5)(v5, &GUID_1725de0f_cf7a_4075_9365_d8c5d1eea8d7, &v13);
  v7 = v6;
  if ( v6 >= 0 )
  {
    v6 = (*(__int64 (__fastcall **)(__int64, __int64, _QWORD, __int64 *, _QWORD))(*(_QWORD *)v13 + 192LL))(
           v13,
           4,
           0,
           &v17,
           0);
    v7 = v6;
    if ( v6 >= 0 )
    {
      if ( v17 )
      {
        v9 = *((_QWORD *)this + 10);
        if ( v9
          && (v6 = (*(__int64 (__fastcall **)(__int64, UINT32 *))(*(_QWORD *)v9 + 240LL))(v9, &cInitialSize),
              v7 = v6,
              v6 < 0) )
        {
          if ( g_wppLevels )
          {
            v8 = 45;
            goto LABEL_39;
          }
        }
        else
        {
          v10 = *(__int64 (__fastcall ***)(SensorGroup *, GUID *, __int64 *))this;
          cInitialSize += 3;
          v6 = (*v10)(this, &GUID_00000000_0000_0000_c000_000000000046, &v14);
          v7 = v6;
          if ( v6 >= 0 )
          {
            v6 = MFCreateAttributes(&ppMFAttributes, cInitialSize);
            v7 = v6;
            if ( v6 >= 0 )
            {
              v11 = *((_QWORD *)this + 10);
              if ( v11
                && (v6 = (*(__int64 (__fastcall **)(__int64, IMFAttributes *))(*(_QWORD *)v11 + 256LL))(
                           v11,
                           ppMFAttributes),
                    v7 = v6,
                    v6 < 0) )
              {
                if ( g_wppLevels )
                {
                  v8 = 48;
                  goto LABEL_39;
                }
              }
              else
              {
                v6 = ((__int64 (__fastcall *)(IMFAttributes *, const IID *, const IID *))ppMFAttributes->lpVtbl->SetGUID)(
                       ppMFAttributes,
                       &MF_DEVSOURCE_ATTRIBUTE_SOURCE_TYPE,
                       &MF_DEVSOURCE_ATTRIBUTE_SOURCE_TYPE_VIDCAP_GUID);
                v7 = v6;
                if ( v6 >= 0 )
                {
                  v6 = ((__int64 (__fastcall *)(IMFAttributes *, const IID *, __int64))ppMFAttributes->lpVtbl->SetString)(
                         ppMFAttributes,
                         &MF_DEVSOURCE_ATTRIBUTE_SOURCE_TYPE_VIDCAP_SYMBOLIC_LINK,
                         v17);
                  v7 = v6;
                  if ( v6 >= 0 )
                  {
                    v6 = ((__int64 (__fastcall *)(IMFAttributes *, __int64 *, __int64))ppMFAttributes->lpVtbl->SetUnknown)(
                           ppMFAttributes,
                           MF_DEVSOURCE_ATTRIBUTE_SENSORGROUP,
                           v14);
                    v7 = v6;
                    if ( v6 >= 0 )
                    {
                      v6 = MFCreateDeviceSource(ppMFAttributes, a2);
                      v7 = v6;
                      if ( v6 >= 0 || !g_wppLevels )
                        goto LABEL_40;
                      v8 = 52;
                      goto LABEL_39;
                    }
                    if ( g_wppLevels )
                    {
                      v8 = 51;
                      goto LABEL_39;
                    }
                  }
                  else if ( g_wppLevels )
                  {
                    v8 = 50;
                    goto LABEL_39;
                  }
                }
                else if ( g_wppLevels )
                {
                  v8 = 49;
                  goto LABEL_39;
                }
              }
            }
            else if ( g_wppLevels )
            {
              v8 = 47;
              goto LABEL_39;
            }
          }
          else if ( g_wppLevels )
          {
            v8 = 46;
            goto LABEL_39;
          }
        }
      }
      else
      {
        v6 = -1072875850;
        v7 = -1072875850;
        if ( g_wppLevels )
        {
          v8 = 44;
          goto LABEL_39;
        }
      }
    }
    else if ( g_wppLevels )
    {
      v8 = 43;
      goto LABEL_39;
    }
  }
  else if ( g_wppLevels )
  {
    v8 = 42;
LABEL_39:
    WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), v8, &WPP_3682f06399713e6eb6d5e127ede867b4_Traceguids, this, v6);
  }
LABEL_40:
  if ( v13 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v13 + 16LL))(v13);
  if ( v14 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v14 + 16LL))(v14);
  v4 = ppMFAttributes;
LABEL_45:
  if ( v4 )
    ((void (__fastcall *)(IMFAttributes *))v4->lpVtbl->Release)(v4);
  return v7;
}

```

## disassembly

```asm
0x180032200  mov     [rsp-18h+arg_8], rbx
0x180032205  push    rbp
0x180032206  push    rsi
0x180032207  push    rdi
0x180032208  mov     rbp, rsp
0x18003220b  sub     rsp, 40h
0x18003220f  mov     rdi, rcx
0x180032212  mov     rsi, rdx
0x180032215  xor     ecx, ecx
0x180032217  mov     [rbp+ppMFAttributes], rcx
0x18003221b  mov     [rbp+var_8], rcx
0x18003221f  mov     r9, [rdi+0B0h]
0x180032226  mov     [rbp+cInitialSize], ecx
0x180032229  mov     [rbp+arg_18], rcx
0x18003222d  mov     [rbp+var_10], rcx
0x180032231  test    r9, r9
0x180032234  jnz     short loc_180032252
0x180032236  mov     eax, 0C00D36B6h
0x18003223b  mov     ebx, eax
0x18003223d  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180032244  jb      loc_1800324DA
0x18003224a  lea     edx, [rcx+29h]
0x18003224d  jmp     loc_18003248E
0x180032252  mov     rax, [r9]
0x180032255  lea     r8, [rbp+var_10]
0x180032259  lea     rdx, _GUID_1725de0f_cf7a_4075_9365_d8c5d1eea8d7
0x180032260  mov     rcx, r9
0x180032263  mov     rax, [rax]
0x180032266  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003226b  mov     ebx, eax
0x18003226d  test    eax, eax
0x18003226f  jns     short loc_180032288
0x180032271  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180032278  jb      loc_1800324AC
0x18003227e  mov     edx, 2Ah ; '*'
0x180032283  jmp     loc_18003248E
0x180032288  mov     rcx, [rbp+var_10]
0x18003228c  lea     r9, [rbp+arg_18]
0x180032290  xor     r8d, r8d
0x180032293  mov     [rsp+40h+var_20], 0
0x18003229c  mov     rax, [rcx]
0x18003229f  lea     edx, [r8+4]
0x1800322a3  mov     rax, [rax+0C0h]
0x1800322aa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800322af  mov     ebx, eax
0x1800322b1  test    eax, eax
0x1800322b3  jns     short loc_1800322CC
0x1800322b5  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1800322bc  jb      loc_1800324AC
0x1800322c2  mov     edx, 2Bh ; '+'
0x1800322c7  jmp     loc_18003248E
0x1800322cc  cmp     [rbp+arg_18], 0
0x1800322d1  jnz     short loc_1800322F1
0x1800322d3  mov     eax, 0C00D36B6h
0x1800322d8  mov     ebx, eax
0x1800322da  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1800322e1  jb      loc_1800324AC
0x1800322e7  mov     edx, 2Ch ; ','
0x1800322ec  jmp     loc_18003248E
0x1800322f1  mov     rcx, [rdi+50h]
0x1800322f5  test    rcx, rcx
0x1800322f8  jz      short loc_18003232A
0x1800322fa  mov     rax, [rcx]
0x1800322fd  lea     rdx, [rbp+cInitialSize]
0x180032301  mov     rax, [rax+0F0h]
0x180032308  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003230d  mov     ebx, eax
0x18003230f  test    eax, eax
0x180032311  jns     short loc_18003232A
0x180032313  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18003231a  jb      loc_1800324AC
0x180032320  mov     edx, 2Dh ; '-'
0x180032325  jmp     loc_18003248E
0x18003232a  mov     rax, [rdi]
0x18003232d  lea     r8, [rbp+var_8]
0x180032331  add     [rbp+cInitialSize], 3
0x180032335  lea     rdx, _GUID_00000000_0000_0000_c000_000000000046
0x18003233c  mov     rcx, rdi
0x18003233f  mov     rax, [rax]
0x180032342  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180032347  mov     ebx, eax
0x180032349  test    eax, eax
0x18003234b  jns     short loc_180032364
0x18003234d  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180032354  jb      loc_1800324AC
0x18003235a  mov     edx, 2Eh ; '.'
0x18003235f  jmp     loc_18003248E
0x180032364  mov     edx, [rbp+cInitialSize]; cInitialSize
0x180032367  lea     rcx, [rbp+ppMFAttributes]; ppMFAttributes
0x18003236b  call    cs:__imp_MFCreateAttributes
0x180032371  mov     ebx, eax
0x180032373  test    eax, eax
0x180032375  jns     short loc_18003238E
0x180032377  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18003237e  jb      loc_1800324AC
0x180032384  mov     edx, 2Fh ; '/'
0x180032389  jmp     loc_18003248E
0x18003238e  mov     rcx, [rdi+50h]
0x180032392  test    rcx, rcx
0x180032395  jz      short loc_1800323C7
0x180032397  mov     rax, [rcx]
0x18003239a  mov     rdx, [rbp+ppMFAttributes]
0x18003239e  mov     rax, [rax+100h]
0x1800323a5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800323aa  mov     ebx, eax
0x1800323ac  test    eax, eax
0x1800323ae  jns     short loc_1800323C7
0x1800323b0  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1800323b7  jb      loc_1800324AC
0x1800323bd  mov     edx, 30h ; '0'
0x1800323c2  jmp     loc_18003248E
0x1800323c7  mov     rcx, [rbp+ppMFAttributes]
0x1800323cb  lea     r8, MF_DEVSOURCE_ATTRIBUTE_SOURCE_TYPE_VIDCAP_GUID
0x1800323d2  lea     rdx, MF_DEVSOURCE_ATTRIBUTE_SOURCE_TYPE
0x1800323d9  mov     rax, [rcx]
0x1800323dc  mov     rax, [rax+0C0h]
0x1800323e3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800323e8  mov     ebx, eax
0x1800323ea  test    eax, eax
0x1800323ec  jns     short loc_180032405
0x1800323ee  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1800323f5  jb      loc_1800324AC
0x1800323fb  mov     edx, 31h ; '1'
0x180032400  jmp     loc_18003248E
0x180032405  mov     rcx, [rbp+ppMFAttributes]
0x180032409  lea     rdx, MF_DEVSOURCE_ATTRIBUTE_SOURCE_TYPE_VIDCAP_SYMBOLIC_LINK
0x180032410  mov     r8, [rbp+arg_18]
0x180032414  mov     rax, [rcx]
0x180032417  mov     rax, [rax+0C8h]
0x18003241e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180032423  mov     ebx, eax
0x180032425  test    eax, eax
0x180032427  jns     short loc_180032439
0x180032429  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180032430  jb      short loc_1800324AC
0x180032432  mov     edx, 32h ; '2'
0x180032437  jmp     short loc_18003248E
0x180032439  mov     rcx, [rbp+ppMFAttributes]
0x18003243d  lea     rdx, MF_DEVSOURCE_ATTRIBUTE_SENSORGROUP
0x180032444  mov     r8, [rbp+var_8]
0x180032448  mov     rax, [rcx]
0x18003244b  mov     rax, [rax+0D8h]
0x180032452  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180032457  mov     ebx, eax
0x180032459  test    eax, eax
0x18003245b  jns     short loc_18003246D
0x18003245d  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180032464  jb      short loc_1800324AC
0x180032466  mov     edx, 33h ; '3'
0x18003246b  jmp     short loc_18003248E
0x18003246d  mov     rcx, [rbp+ppMFAttributes]; pAttributes
0x180032471  mov     rdx, rsi; ppSource
0x180032474  call    cs:__imp_MFCreateDeviceSource
0x18003247a  mov     ebx, eax
0x18003247c  test    eax, eax
0x18003247e  jns     short loc_1800324AC
0x180032480  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180032487  jb      short loc_1800324AC
0x180032489  mov     edx, 34h ; '4'
0x18003248e  mov     rcx, cs:WPP_GLOBAL_Control
0x180032495  lea     r8, WPP_3682f06399713e6eb6d5e127ede867b4_Traceguids
0x18003249c  mov     r9, rdi
0x18003249f  mov     dword ptr [rsp+40h+var_20], eax
0x1800324a3  mov     rcx, [rcx+10h]
0x1800324a7  call    WPP_SF_qD
0x1800324ac  mov     rcx, [rbp+var_10]
0x1800324b0  test    rcx, rcx
0x1800324b3  jz      short loc_1800324C1
0x1800324b5  mov     rax, [rcx]
0x1800324b8  mov     rax, [rax+10h]
0x1800324bc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800324c1  mov     rcx, [rbp+var_8]
0x1800324c5  test    rcx, rcx
0x1800324c8  jz      short loc_1800324D6
0x1800324ca  mov     rax, [rcx]
0x1800324cd  mov     rax, [rax+10h]
0x1800324d1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800324d6  mov     rcx, [rbp+ppMFAttributes]
0x1800324da  test    rcx, rcx
0x1800324dd  jz      short loc_1800324EB
0x1800324df  mov     rax, [rcx]
0x1800324e2  mov     rax, [rax+10h]
0x1800324e6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800324eb  mov     eax, ebx
0x1800324ed  mov     rbx, [rsp+40h+arg_8]
0x1800324f2  add     rsp, 40h
0x1800324f6  pop     rdi
0x1800324f7  pop     rsi
0x1800324f8  pop     rbp
0x1800324f9  retn
```
