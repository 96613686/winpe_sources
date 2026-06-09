# CApplication::UpdateVolume(__MIDL___MIDL_itf_audiosrv_0000_0000_0004,int *,int *)

- ea: `0x180017200`
- end: `0x18001745e`
- name: `?UpdateVolume@CApplication@@IEAAXW4__MIDL___MIDL_itf_audiosrv_0000_0000_0004@@PEAH1@Z`
- size: `606`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: `registry_config, installer_update`

## callers

- `0x1800161d0`
- `0x180016a30`

## callees

- `0x180017200`
- `0x18001d580`
- `0x180031960`

## import_xrefs

- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x180017418`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x180017418`

## pseudocode

```c
int __fastcall CApplication::UpdateVolume(__int64 a1, int a2, BOOL *a3, int *a4)
{
  __int64 v4; // rax
  BOOL v8; // r12d
  BOOL v10; // esi
  BOOL v11; // r13d
  __int64 v12; // r10
  const wchar_t *v13; // rdx
  const wchar_t *v14; // r8
  int v15; // ecx
  int v16; // ecx
  __int64 v17; // rcx
  __int64 *v18; // r9
  __int64 v19; // rax
  bool v20; // zf
  __int64 v21; // rax
  int v22; // ecx
  __int64 v24; // [rsp+38h] [rbp-61h] BYREF
  EVENT_DESCRIPTOR EventDescriptor; // [rsp+40h] [rbp-59h] BYREF
  struct _EVENT_DATA_DESCRIPTOR UserData; // [rsp+50h] [rbp-49h] BYREF
  char *v27; // [rsp+60h] [rbp-39h]
  int v28; // [rsp+68h] [rbp-31h]
  int v29; // [rsp+6Ch] [rbp-2Dh]
  __int64 *v30; // [rsp+70h] [rbp-29h]
  int v31; // [rsp+78h] [rbp-21h]
  int v32; // [rsp+7Ch] [rbp-1Dh]
  __int64 *v33; // [rsp+80h] [rbp-19h]
  __int64 v34; // [rsp+88h] [rbp-11h]
  const wchar_t *v35; // [rsp+90h] [rbp-9h]
  int v36; // [rsp+98h] [rbp-1h]
  int v37; // [rsp+9Ch] [rbp+3h]
  const wchar_t *v38; // [rsp+A0h] [rbp+7h]
  int v39; // [rsp+A8h] [rbp+Fh]
  int v40; // [rsp+ACh] [rbp+13h]

  LODWORD(v4) = *(_DWORD *)(a1 + 216);
  v8 = v4 != a2;
  v10 = v4 == 0;
  v11 = a2 == 0;
  if ( (_DWORD)v4 != a2 )
  {
    v12 = *((_QWORD *)AudioSrvPolicyManagerTelemetryProvider::Instance() + 1);
    LODWORD(v4) = *(_DWORD *)v12;
    if ( *(_DWORD *)v12 > 4u )
    {
      v4 = *(_QWORD *)(v12 + 16);
      if ( (v4 & 0x20000) != 0 )
      {
        v4 = *(_QWORD *)(v12 + 24) & 0x20000LL;
        if ( v4 == *(_QWORD *)(v12 + 24) )
        {
          v13 = L"Unknown level";
          if ( a2 )
          {
            if ( a2 == 1 )
            {
              v14 = L"SNDLVL_Low";
            }
            else if ( a2 == 2 )
            {
              v14 = L"SNDLVL_Full";
            }
            else
            {
              v14 = L"Unknown level";
            }
          }
          else
          {
            v14 = L"SNDLVL_Muted";
          }
          v15 = *(_DWORD *)(a1 + 216);
          if ( v15 )
          {
            v16 = v15 - 1;
            if ( v16 )
            {
              if ( v16 == 1 )
                v13 = L"SNDLVL_Full";
            }
            else
            {
              v13 = L"SNDLVL_Low";
            }
          }
          else
          {
            v13 = L"SNDLVL_Muted";
          }
          v17 = -1;
          v18 = *(__int64 **)(a1 + 24);
          v24 = *(_QWORD *)(a1 + 696);
          v19 = -1;
          do
            v20 = v14[++v19] == 0;
          while ( !v20 );
          v38 = v14;
          v39 = 2 * v19 + 2;
          v40 = 0;
          v21 = -1;
          do
            v20 = v13[++v21] == 0;
          while ( !v20 );
          v35 = v13;
          v36 = 2 * v21 + 2;
          v33 = &v24;
          v37 = 0;
          v34 = 8;
          if ( v18 )
          {
            do
              v20 = *((_WORD *)v18 + ++v17) == 0;
            while ( !v20 );
            v22 = 2 * v17 + 2;
          }
          else
          {
            v18 = &qword_180053B30;
            v22 = 2;
          }
          *(_DWORD *)&EventDescriptor.Level = 4;
          UserData.Ptr = *(_QWORD *)(v12 + 8);
          v31 = v22;
          v30 = v18;
          v32 = 0;
          *(_DWORD *)&EventDescriptor.Id = 184549376;
          EventDescriptor.Keyword = 0x20000;
          UserData.Size = *(unsigned __int16 *)UserData.Ptr;
          v27 = &byte_180057477;
          UserData.Reserved = 2;
          v28 = 77;
          v29 = 1;
          LODWORD(v4) = EventWriteTransfer(*(_QWORD *)(v12 + 32), &EventDescriptor, 0, 0, 6u, &UserData);
        }
      }
    }
  }
  if ( a3 )
    *a3 = v8;
  if ( a4 )
    *a4 = v11 ^ v10;
  *(_DWORD *)(a1 + 216) = a2;
  return v4;
}

```

## disassembly

```asm
0x180017200  mov     [rsp-8+arg_8], rbx
0x180017205  push    rbp
0x180017206  push    rsi
0x180017207  push    rdi
0x180017208  push    r12
0x18001720a  push    r13
0x18001720c  push    r14
0x18001720e  push    r15
0x180017210  lea     rbp, [rsp-27h]
0x180017215  sub     rsp, 0C0h
0x18001721c  mov     rax, cs:__security_cookie
0x180017223  xor     rax, rsp
0x180017226  mov     [rbp+57h+var_40], rax
0x18001722a  mov     eax, [rcx+0D8h]
0x180017230  xor     r12d, r12d
0x180017233  cmp     eax, edx
0x180017235  mov     r14, r9
0x180017238  mov     r15, r8
0x18001723b  mov     edi, edx
0x18001723d  setnz   r12b
0x180017241  mov     rbx, rcx
0x180017244  xor     esi, esi
0x180017246  test    eax, eax
0x180017248  setz    sil
0x18001724c  xor     r13d, r13d
0x18001724f  test    edx, edx
0x180017251  setz    r13b
0x180017255  cmp     eax, edx
0x180017257  jz      loc_18001741E
0x18001725d  call    ?Instance@AudioSrvPolicyManagerTelemetryProvider@@KAPEAV1@XZ; AudioSrvPolicyManagerTelemetryProvider::Instance(void)
0x180017262  mov     r10, [rax+8]
0x180017266  mov     eax, [r10]
0x180017269  cmp     eax, 4
0x18001726c  jbe     loc_18001741E
0x180017272  mov     rcx, [r10+18h]
0x180017276  mov     rax, [r10+10h]
0x18001727a  bt      rax, 11h
0x18001727f  jnb     loc_18001741E
0x180017285  mov     rax, rcx
0x180017288  and     eax, 20000h
0x18001728d  cmp     rax, rcx
0x180017290  jnz     loc_18001741E
0x180017296  lea     rdx, aUnknownLevel; "Unknown level"
0x18001729d  mov     ecx, edi
0x18001729f  test    edi, edi
0x1800172a1  jz      short loc_1800172C4
0x1800172a3  sub     ecx, 1
0x1800172a6  jz      short loc_1800172BB
0x1800172a8  cmp     ecx, 1
0x1800172ab  jz      short loc_1800172B2
0x1800172ad  mov     r8, rdx
0x1800172b0  jmp     short loc_1800172CB
0x1800172b2  lea     r8, aSndlvlFull; "SNDLVL_Full"
0x1800172b9  jmp     short loc_1800172CB
0x1800172bb  lea     r8, aSndlvlLow; "SNDLVL_Low"
0x1800172c2  jmp     short loc_1800172CB
0x1800172c4  lea     r8, aSndlvlMuted; "SNDLVL_Muted"
0x1800172cb  mov     ecx, [rbx+0D8h]
0x1800172d1  test    ecx, ecx
0x1800172d3  jz      short loc_1800172F1
0x1800172d5  sub     ecx, 1
0x1800172d8  jz      short loc_1800172E8
0x1800172da  cmp     ecx, 1
0x1800172dd  jnz     short loc_1800172F8
0x1800172df  lea     rdx, aSndlvlFull; "SNDLVL_Full"
0x1800172e6  jmp     short loc_1800172F8
0x1800172e8  lea     rdx, aSndlvlLow; "SNDLVL_Low"
0x1800172ef  jmp     short loc_1800172F8
0x1800172f1  lea     rdx, aSndlvlMuted; "SNDLVL_Muted"
0x1800172f8  mov     rax, [rbx+2B8h]
0x1800172ff  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x180017306  mov     r9, [rbx+18h]
0x18001730a  mov     [rbp+57h+var_B8], rax
0x18001730e  mov     rax, rcx
0x180017311  cmp     word ptr [r8+rax*2+2], 0
0x180017318  lea     rax, [rax+1]
0x18001731c  jnz     short loc_180017311
0x18001731e  lea     eax, ds:2[rax*2]
0x180017325  mov     [rbp+57h+var_50], r8
0x180017329  xor     r8d, r8d; ActivityId
0x18001732c  mov     [rbp+57h+var_48], eax
0x18001732f  mov     [rbp+57h+var_44], r8d
0x180017333  mov     rax, rcx
0x180017336  nop     word ptr [rax+rax+00000000h]
0x180017340  cmp     [rdx+rax*2+2], r8w
0x180017346  lea     rax, [rax+1]
0x18001734a  jnz     short loc_180017340
0x18001734c  mov     [rbp+57h+var_60], rdx
0x180017350  lea     eax, ds:2[rax*2]
0x180017357  mov     [rbp+57h+var_58], eax
0x18001735a  lea     rax, [rbp+57h+var_B8]
0x18001735e  mov     [rbp+57h+var_70], rax
0x180017362  mov     [rbp+57h+var_54], r8d
0x180017366  mov     [rbp+57h+var_68], 8
0x18001736e  test    r9, r9
0x180017371  jz      short loc_180017388
0x180017373  cmp     [r9+rcx*2+2], r8w
0x180017379  lea     rcx, [rcx+1]
0x18001737d  jnz     short loc_180017373
0x18001737f  lea     ecx, ds:2[rcx*2]
0x180017386  jmp     short loc_180017394
0x180017388  lea     r9, qword_180053B30
0x18001738f  mov     ecx, 2
0x180017394  movzx   eax, cs:word_18005746D
0x18001739b  lea     rdx, [rbp+57h+EventDescriptor]; EventDescriptor
0x18001739f  mov     dword ptr [rbp+57h+EventDescriptor.Level], eax
0x1800173a2  mov     rax, [r10+8]
0x1800173a6  mov     [rbp+57h+var_A0.Ptr], rax
0x1800173aa  mov     [rbp+57h+var_78], ecx
0x1800173ad  lea     rcx, _TraceLoggingMetadata
0x1800173b4  mov     [rbp+57h+var_80], r9
0x1800173b8  xor     r9d, r9d; RelatedActivityId
0x1800173bb  mov     [rbp+57h+var_74], r8d
0x1800173bf  mov     dword ptr [rbp+57h+EventDescriptor.Id], 0B000000h
0x1800173c6  mov     [rbp+57h+EventDescriptor.Keyword], 20000h
0x1800173ce  movzx   eax, word ptr [rax]
0x1800173d1  mov     [rbp+57h+var_A0.Size], eax
0x1800173d4  lea     rax, byte_180057477
0x1800173db  mov     [rbp+57h+var_90], rax
0x1800173df  lea     rax, _TraceLoggingMetadataEnd
0x1800173e6  sub     eax, ecx
0x1800173e8  mov     dword ptr [rbp+57h+var_A0.0Ch], 2
0x1800173ef  mov     [rbp+57h+var_88], 4Dh ; 'M'
0x1800173f6  mov     [rbp+57h+var_84], 1
0x1800173fd  mov     [rbp+57h+var_C0], eax
0x180017400  mov     eax, [rbp+57h+var_C0]
0x180017403  mov     rcx, [r10+20h]; RegHandle
0x180017407  lea     rax, [rbp+57h+var_A0]
0x18001740b  mov     [rsp+0F0h+UserData], rax; UserData
0x180017410  mov     [rsp+0F0h+UserDataCount], 6; UserDataCount
0x180017418  call    cs:__imp_EventWriteTransfer
0x18001741e  test    r15, r15
0x180017421  jz      short loc_180017426
0x180017423  mov     [r15], r12d
0x180017426  test    r14, r14
0x180017429  jz      short loc_180017431
0x18001742b  xor     esi, r13d
0x18001742e  mov     [r14], esi
0x180017431  mov     [rbx+0D8h], edi
0x180017437  mov     rcx, [rbp+57h+var_40]
0x18001743b  xor     rcx, rsp; StackCookie
0x18001743e  call    __security_check_cookie
0x180017443  mov     rbx, [rsp+0F0h+arg_8]
0x18001744b  add     rsp, 0C0h
0x180017452  pop     r15
0x180017454  pop     r14
0x180017456  pop     r13
0x180017458  pop     r12
0x18001745a  pop     rdi
0x18001745b  pop     rsi
0x18001745c  pop     rbp
0x18001745d  retn
```
