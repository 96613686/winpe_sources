# sub_1801DCFC0

- ea: `0x1801dcfc0`
- end: `0x1801dd771`
- name: `sub_1801DCFC0`
- size: `1969`
- prototype: ``
- caller_count: `0`
- callee_count: `9`
- tags: `installer_update`

## callees

- `0x18002fee0`
- `0x18003ecb0`
- `0x1800402c0`
- `0x180050d6c`
- `0x180063f00`
- `0x1800ec0e0`
- `0x1801dcfc0`
- `0x180258480`
- `0x180344d40`

## import_xrefs

- `MFPlat!MFCreateMediaType` at `0x1801dd36e`
- `MFPlat!MFCreateMediaType` at `0x1801dd36e`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1801dd0a1`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1801dd16d`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1801dd225`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1801dd2e0`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1801dd390`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1801dd44a`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1801dd502`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1801dd5bc`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1801dd679`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1801dd0a1`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1801dd16d`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1801dd225`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1801dd2e0`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1801dd390`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1801dd44a`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1801dd502`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1801dd5bc`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1801dd679`

## string_xrefs

- `0x1801dcff0`: `CMediaSession::UpdateOutputTypeGUID`
- `0x1801dd0ff`: `CMediaSession::UpdateOutputTypeGUID`
- `0x1801dd1cb`: `CMediaSession::UpdateOutputTypeGUID`
- `0x1801dd283`: `CMediaSession::UpdateOutputTypeGUID`
- `0x1801dd33e`: `CMediaSession::UpdateOutputTypeGUID`
- `0x1801dd3ee`: `CMediaSession::UpdateOutputTypeGUID`
- `0x1801dd4a8`: `CMediaSession::UpdateOutputTypeGUID`
- `0x1801dd560`: `CMediaSession::UpdateOutputTypeGUID`
- `0x1801dd61a`: `CMediaSession::UpdateOutputTypeGUID`
- `0x1801dd6d7`: `CMediaSession::UpdateOutputTypeGUID`

## pseudocode

```c
__int64 __fastcall sub_1801DCFC0(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  __int64 *v8; // rcx
  __int64 v9; // rdi
  int v10; // ebx
  __int128 *v11; // rax
  __int128 v12; // xmm0
  HRESULT v13; // ebx
  __int64 v14; // rax
  __int64 v15; // rax
  __int64 v16; // r9
  __int64 v17; // rdx
  __int64 *v18; // rcx
  __int64 v19; // rax
  __int64 v20; // rax
  __int64 *v21; // rcx
  __int64 v22; // rax
  __int64 v23; // rax
  __int64 *v24; // rcx
  __int64 v25; // rax
  __int64 v26; // rax
  __int64 *v27; // rcx
  __int64 v28; // rax
  __int64 v29; // rax
  __int64 *v30; // rcx
  __int64 v31; // rax
  __int64 v32; // rax
  __int64 *v33; // rcx
  __int64 v34; // rax
  __int64 v35; // rax
  __int64 *v36; // rcx
  __int64 v37; // rax
  __int64 v38; // rax
  __int64 *v39; // rcx
  __int64 v40; // rax
  __int64 v41; // rax
  _BYTE v43[8]; // [rsp+30h] [rbp-39h] BYREF
  IMFMediaType *ppMFType; // [rsp+38h] [rbp-31h] BYREF
  __int64 v45; // [rsp+40h] [rbp-29h] BYREF
  __int64 v46; // [rsp+48h] [rbp-21h] BYREF
  __int64 (__fastcall ***v47)(_QWORD, const IID *, __int64 *); // [rsp+50h] [rbp-19h] BYREF
  __int64 v48; // [rsp+58h] [rbp-11h] BYREF
  _BYTE v49[16]; // [rsp+60h] [rbp-9h] BYREF

  sub_18002FEE0(v43, "CMediaSession::UpdateOutputTypeGUID", 9562);
  v8 = (__int64 *)qword_1803CEF18;
  if ( *(_BYTE *)(qword_1803CEF18 + 8) && *(_QWORD *)(a1 + 1088) )
  {
    v9 = sub_1800402C0(qword_1803CEF18);
    v10 = (*(__int64 (__fastcall **)(_QWORD))(**(_QWORD **)(a1 + 1088) + 296LL))(*(_QWORD *)(a1 + 1088));
    v11 = (__int128 *)(*(__int64 (__fastcall **)(_QWORD, _BYTE *))(**(_QWORD **)(a1 + 1088) + 280LL))(
                        *(_QWORD *)(a1 + 1088),
                        v49);
    v8 = (__int64 *)qword_1803CEF18;
    v12 = *v11;
    *(_DWORD *)(v9 + 2016) = v10;
    *(_OWORD *)(v9 + 2000) = v12;
  }
  v48 = 0;
  v47 = 0;
  v45 = 0;
  v46 = 0;
  ppMFType = 0;
  if ( *(_QWORD *)(a1 + 480) )
  {
    v13 = (*(__int64 (__fastcall **)(_QWORD, __int64, __int64 *))(**(_QWORD **)(a1 - 528 + 1008) + 320LL))(
            *(_QWORD *)(a1 - 528 + 1008),
            a2,
            &v48);
    if ( v13 >= 0 )
    {
      v13 = (*(__int64 (__fastcall **)(__int64, __int64 (__fastcall ****)(_QWORD, const IID *, __int64 *)))(*(_QWORD *)v48 + 272LL))(
              v48,
              &v47);
      if ( v13 >= 0 )
      {
        v13 = (**v47)(v47, &stru_180367B40, &v45);
        if ( v13 >= 0 )
        {
          v13 = MFCreateMediaType(&ppMFType);
          if ( v13 >= 0 )
          {
            v13 = (*(__int64 (__fastcall **)(__int64, _QWORD, __int64 *))(*(_QWORD *)v45 + 144LL))(v45, 0, &v46);
            if ( v13 >= 0 )
            {
              v13 = (*(__int64 (__fastcall **)(__int64, IMFMediaType *))(*(_QWORD *)v46 + 256LL))(v46, ppMFType);
              if ( v13 >= 0 )
              {
                v13 = ((__int64 (__fastcall *)(IMFMediaType *, __int64, __int64))ppMFType->lpVtbl->SetGUID)(
                        ppMFType,
                        a3,
                        a4);
                if ( v13 >= 0 )
                {
                  v13 = (*(__int64 (__fastcall **)(__int64, _QWORD, IMFMediaType *, _QWORD))(*(_QWORD *)v45 + 128LL))(
                          v45,
                          0,
                          ppMFType,
                          0);
                  if ( v13 >= 0 )
                    goto LABEL_105;
                  v39 = (__int64 *)qword_1803CEF18;
                  if ( !qword_1803CEF18 )
                  {
                    v40 = MFGetCallStackTracingWeakReference(0);
                    qword_1803CEF18 = v40;
                    if ( v40 && (*(unsigned int (__fastcall **)(__int64, __int64))(*(_QWORD *)v40 + 8LL))(v40, 2032) )
                    {
                      v39 = (__int64 *)qword_1803CEF18;
                    }
                    else
                    {
                      v39 = &qword_1803CE250;
                      qword_1803CEF18 = (__int64)&qword_1803CE250;
                    }
                  }
                  if ( *((_BYTE *)v39 + 8) )
                  {
                    v41 = sub_1800402C0(v39);
                    if ( *(_DWORD *)(v41 + 1996) != v13 )
                      sub_1800EC0E0(v41, "CMediaSession::UpdateOutputTypeGUID", 9584, (unsigned int)v13);
                  }
                  if ( !byte_1803CECE8 )
                    goto LABEL_105;
                  v17 = 760;
                }
                else
                {
                  v36 = (__int64 *)qword_1803CEF18;
                  if ( !qword_1803CEF18 )
                  {
                    v37 = MFGetCallStackTracingWeakReference(0);
                    qword_1803CEF18 = v37;
                    if ( v37 && (*(unsigned int (__fastcall **)(__int64, __int64))(*(_QWORD *)v37 + 8LL))(v37, 2032) )
                    {
                      v36 = (__int64 *)qword_1803CEF18;
                    }
                    else
                    {
                      v36 = &qword_1803CE250;
                      qword_1803CEF18 = (__int64)&qword_1803CE250;
                    }
                  }
                  if ( *((_BYTE *)v36 + 8) )
                  {
                    v38 = sub_1800402C0(v36);
                    if ( *(_DWORD *)(v38 + 1996) != v13 )
                      sub_1800EC0E0(v38, "CMediaSession::UpdateOutputTypeGUID", 9583, (unsigned int)v13);
                  }
                  if ( !byte_1803CECE8 )
                    goto LABEL_105;
                  v17 = 759;
                }
              }
              else
              {
                v33 = (__int64 *)qword_1803CEF18;
                if ( !qword_1803CEF18 )
                {
                  v34 = MFGetCallStackTracingWeakReference(0);
                  qword_1803CEF18 = v34;
                  if ( v34 && (*(unsigned int (__fastcall **)(__int64, __int64))(*(_QWORD *)v34 + 8LL))(v34, 2032) )
                  {
                    v33 = (__int64 *)qword_1803CEF18;
                  }
                  else
                  {
                    v33 = &qword_1803CE250;
                    qword_1803CEF18 = (__int64)&qword_1803CE250;
                  }
                }
                if ( *((_BYTE *)v33 + 8) )
                {
                  v35 = sub_1800402C0(v33);
                  if ( *(_DWORD *)(v35 + 1996) != v13 )
                    sub_1800EC0E0(v35, "CMediaSession::UpdateOutputTypeGUID", 9582, (unsigned int)v13);
                }
                if ( !byte_1803CECE8 )
                  goto LABEL_105;
                v17 = 758;
              }
            }
            else
            {
              v30 = (__int64 *)qword_1803CEF18;
              if ( !qword_1803CEF18 )
              {
                v31 = MFGetCallStackTracingWeakReference(0);
                qword_1803CEF18 = v31;
                if ( v31 && (*(unsigned int (__fastcall **)(__int64, __int64))(*(_QWORD *)v31 + 8LL))(v31, 2032) )
                {
                  v30 = (__int64 *)qword_1803CEF18;
                }
                else
                {
                  v30 = &qword_1803CE250;
                  qword_1803CEF18 = (__int64)&qword_1803CE250;
                }
              }
              if ( *((_BYTE *)v30 + 8) )
              {
                v32 = sub_1800402C0(v30);
                if ( *(_DWORD *)(v32 + 1996) != v13 )
                  sub_1800EC0E0(v32, "CMediaSession::UpdateOutputTypeGUID", 9581, (unsigned int)v13);
              }
              if ( !byte_1803CECE8 )
                goto LABEL_105;
              v17 = 757;
            }
          }
          else
          {
            v27 = (__int64 *)qword_1803CEF18;
            if ( !qword_1803CEF18 )
            {
              v28 = MFGetCallStackTracingWeakReference(0);
              qword_1803CEF18 = v28;
              if ( v28 && (*(unsigned int (__fastcall **)(__int64, __int64))(*(_QWORD *)v28 + 8LL))(v28, 2032) )
              {
                v27 = (__int64 *)qword_1803CEF18;
              }
              else
              {
                v27 = &qword_1803CE250;
                qword_1803CEF18 = (__int64)&qword_1803CE250;
              }
            }
            if ( *((_BYTE *)v27 + 8) )
            {
              v29 = sub_1800402C0(v27);
              if ( *(_DWORD *)(v29 + 1996) != v13 )
                sub_1800EC0E0(v29, "CMediaSession::UpdateOutputTypeGUID", 9580, (unsigned int)v13);
            }
            if ( !byte_1803CECE8 )
              goto LABEL_105;
            v17 = 756;
          }
        }
        else
        {
          v24 = (__int64 *)qword_1803CEF18;
          if ( !qword_1803CEF18 )
          {
            v25 = MFGetCallStackTracingWeakReference(0);
            qword_1803CEF18 = v25;
            if ( v25 && (*(unsigned int (__fastcall **)(__int64, __int64))(*(_QWORD *)v25 + 8LL))(v25, 2032) )
            {
              v24 = (__int64 *)qword_1803CEF18;
            }
            else
            {
              v24 = &qword_1803CE250;
              qword_1803CEF18 = (__int64)&qword_1803CE250;
            }
          }
          if ( *((_BYTE *)v24 + 8) )
          {
            v26 = sub_1800402C0(v24);
            if ( *(_DWORD *)(v26 + 1996) != v13 )
              sub_1800EC0E0(v26, "CMediaSession::UpdateOutputTypeGUID", 9578, (unsigned int)v13);
          }
          if ( !byte_1803CECE8 )
            goto LABEL_105;
          v17 = 755;
        }
      }
      else
      {
        v21 = (__int64 *)qword_1803CEF18;
        if ( !qword_1803CEF18 )
        {
          v22 = MFGetCallStackTracingWeakReference(0);
          qword_1803CEF18 = v22;
          if ( v22 && (*(unsigned int (__fastcall **)(__int64, __int64))(*(_QWORD *)v22 + 8LL))(v22, 2032) )
          {
            v21 = (__int64 *)qword_1803CEF18;
          }
          else
          {
            v21 = &qword_1803CE250;
            qword_1803CEF18 = (__int64)&qword_1803CE250;
          }
        }
        if ( *((_BYTE *)v21 + 8) )
        {
          v23 = sub_1800402C0(v21);
          if ( *(_DWORD *)(v23 + 1996) != v13 )
            sub_1800EC0E0(v23, "CMediaSession::UpdateOutputTypeGUID", 9577, (unsigned int)v13);
        }
        if ( !byte_1803CECE8 )
          goto LABEL_105;
        v17 = 754;
      }
    }
    else
    {
      v18 = (__int64 *)qword_1803CEF18;
      if ( !qword_1803CEF18 )
      {
        v19 = MFGetCallStackTracingWeakReference(0);
        qword_1803CEF18 = v19;
        if ( v19 && (*(unsigned int (__fastcall **)(__int64, __int64))(*(_QWORD *)v19 + 8LL))(v19, 2032) )
        {
          v18 = (__int64 *)qword_1803CEF18;
        }
        else
        {
          v18 = &qword_1803CE250;
          qword_1803CEF18 = (__int64)&qword_1803CE250;
        }
      }
      if ( *((_BYTE *)v18 + 8) )
      {
        v20 = sub_1800402C0(v18);
        if ( *(_DWORD *)(v20 + 1996) != v13 )
          sub_1800EC0E0(v20, "CMediaSession::UpdateOutputTypeGUID", 9576, (unsigned int)v13);
      }
      if ( !byte_1803CECE8 )
        goto LABEL_105;
      v17 = 753;
    }
    v16 = a1 - 528;
    goto LABEL_104;
  }
  v13 = -1072875854;
  if ( !v8 )
  {
    v14 = MFGetCallStackTracingWeakReference(0);
    qword_1803CEF18 = v14;
    if ( v14 && (*(unsigned int (__fastcall **)(__int64, __int64))(*(_QWORD *)v14 + 8LL))(v14, 2032) )
    {
      v8 = (__int64 *)qword_1803CEF18;
    }
    else
    {
      v8 = &qword_1803CE250;
      qword_1803CEF18 = (__int64)&qword_1803CE250;
    }
  }
  if ( *((_BYTE *)v8 + 8) )
  {
    v15 = sub_1800402C0(v8);
    if ( *(_DWORD *)(v15 + 1996) != -1072875854 )
      sub_1800EC0E0(v15, "CMediaSession::UpdateOutputTypeGUID", 9573, 3222091442LL);
  }
  if ( byte_1803CECE8 )
  {
    v16 = a1 - 528;
    v17 = 752;
LABEL_104:
    sub_180050D6C(*((_QWORD *)RequestContext + 2), v17, &stru_180365588, v16, v13);
  }
LABEL_105:
  sub_180063F00(&ppMFType);
  sub_180063F00(&v46);
  sub_180063F00(&v45);
  sub_180063F00(&v47);
  sub_180063F00(&v48);
  sub_18003ECB0(v43);
  return (unsigned int)v13;
}

```

## disassembly

```asm
0x1801dcfc0  push    rbp
0x1801dcfc2  push    rbx
0x1801dcfc3  push    rsi
0x1801dcfc4  push    rdi
0x1801dcfc5  push    r12
0x1801dcfc7  push    r13
0x1801dcfc9  push    r14
0x1801dcfcb  push    r15
0x1801dcfcd  lea     rbp, [rsp-1Fh]
0x1801dcfd2  sub     rsp, 88h
0x1801dcfd9  mov     rax, cs:__security_cookie
0x1801dcfe0  xor     rax, rsp
0x1801dcfe3  mov     [rbp+57h+var_50], rax
0x1801dcfe7  mov     r15, r8
0x1801dcfea  mov     r14, rdx
0x1801dcfed  mov     rsi, rcx
0x1801dcff0  lea     rdx, aCmediasessionU_2; "CMediaSession::UpdateOutputTypeGUID"
0x1801dcff7  mov     r8d, 255Ah
0x1801dcffd  lea     rcx, [rbp+57h+var_90]
0x1801dd001  mov     r12, r9
0x1801dd004  call    sub_18002FEE0
0x1801dd009  mov     rcx, cs:qword_1803CEF18
0x1801dd010  xor     r13d, r13d
0x1801dd013  cmp     [rcx+8], r13b
0x1801dd017  jz      short loc_1801DD076
0x1801dd019  cmp     [rsi+440h], r13
0x1801dd020  jz      short loc_1801DD076
0x1801dd022  call    sub_1800402C0
0x1801dd027  mov     rcx, [rsi+440h]
0x1801dd02e  mov     rdi, rax
0x1801dd031  mov     rdx, [rcx]
0x1801dd034  mov     rax, [rdx+128h]
0x1801dd03b  call    cs:__guard_dispatch_icall_fptr
0x1801dd041  mov     rcx, [rsi+440h]
0x1801dd048  mov     ebx, eax
0x1801dd04a  mov     rdx, [rcx]
0x1801dd04d  mov     rax, [rdx+118h]
0x1801dd054  lea     rdx, [rbp+57h+var_60]
0x1801dd058  call    cs:__guard_dispatch_icall_fptr
0x1801dd05e  mov     rcx, cs:qword_1803CEF18
0x1801dd065  movups  xmm0, xmmword ptr [rax]
0x1801dd068  mov     [rdi+7E0h], ebx
0x1801dd06e  movdqu  xmmword ptr [rdi+7D0h], xmm0
0x1801dd076  mov     [rbp+57h+var_68], r13
0x1801dd07a  mov     [rbp+57h+var_70], r13
0x1801dd07e  mov     [rbp+57h+var_80], r13
0x1801dd082  mov     [rbp+57h+var_78], r13
0x1801dd086  mov     [rbp+57h+ppMFType], r13
0x1801dd08a  cmp     [rsi+1E0h], r13
0x1801dd091  jnz     loc_1801DD132
0x1801dd097  mov     ebx, 0C00D36B2h
0x1801dd09c  test    rcx, rcx
0x1801dd09f  jnz     short loc_1801DD0E9
0x1801dd0a1  call    cs:MFGetCallStackTracingWeakReference
0x1801dd0a8  nop     dword ptr [rax+rax+00h]
0x1801dd0ad  mov     cs:qword_1803CEF18, rax
0x1801dd0b4  mov     rcx, rax
0x1801dd0b7  test    rax, rax
0x1801dd0ba  jz      short loc_1801DD0DB
0x1801dd0bc  mov     rax, [rax]
0x1801dd0bf  mov     edx, 7F0h
0x1801dd0c4  mov     rax, [rax+8]
0x1801dd0c8  call    cs:__guard_dispatch_icall_fptr
0x1801dd0ce  test    eax, eax
0x1801dd0d0  jz      short loc_1801DD0DB
0x1801dd0d2  mov     rcx, cs:qword_1803CEF18
0x1801dd0d9  jmp     short loc_1801DD0E9
0x1801dd0db  lea     rcx, qword_1803CE250
0x1801dd0e2  mov     cs:qword_1803CEF18, rcx
0x1801dd0e9  cmp     [rcx+8], r13b
0x1801dd0ed  jz      short loc_1801DD114
0x1801dd0ef  call    sub_1800402C0
0x1801dd0f4  cmp     [rax+7CCh], ebx
0x1801dd0fa  jz      short loc_1801DD114
0x1801dd0fc  mov     r9d, ebx
0x1801dd0ff  lea     rdx, aCmediasessionU_2; "CMediaSession::UpdateOutputTypeGUID"
0x1801dd106  mov     r8d, 2565h
0x1801dd10c  mov     rcx, rax
0x1801dd10f  call    sub_1800EC0E0
0x1801dd114  cmp     cs:byte_1803CECE8, 1
0x1801dd11b  jb      loc_1801DD718
0x1801dd121  lea     r9, [rsi-210h]
0x1801dd128  mov     edx, 2F0h
0x1801dd12d  jmp     loc_1801DD6FD
0x1801dd132  lea     rdi, [rsi-210h]
0x1801dd139  mov     rdx, r14
0x1801dd13c  mov     rcx, [rdi+3F0h]
0x1801dd143  lea     r8, [rbp+57h+var_68]
0x1801dd147  mov     rax, [rcx]
0x1801dd14a  mov     rax, [rax+140h]
0x1801dd151  call    cs:__guard_dispatch_icall_fptr
0x1801dd157  mov     ebx, eax
0x1801dd159  test    eax, eax
0x1801dd15b  jns     loc_1801DD1F7
0x1801dd161  mov     rcx, cs:qword_1803CEF18
0x1801dd168  test    rcx, rcx
0x1801dd16b  jnz     short loc_1801DD1B5
0x1801dd16d  call    cs:MFGetCallStackTracingWeakReference
0x1801dd174  nop     dword ptr [rax+rax+00h]
0x1801dd179  mov     cs:qword_1803CEF18, rax
0x1801dd180  mov     rcx, rax
0x1801dd183  test    rax, rax
0x1801dd186  jz      short loc_1801DD1A7
0x1801dd188  mov     rax, [rax]
0x1801dd18b  mov     edx, 7F0h
0x1801dd190  mov     rax, [rax+8]
0x1801dd194  call    cs:__guard_dispatch_icall_fptr
0x1801dd19a  test    eax, eax
0x1801dd19c  jz      short loc_1801DD1A7
0x1801dd19e  mov     rcx, cs:qword_1803CEF18
0x1801dd1a5  jmp     short loc_1801DD1B5
0x1801dd1a7  lea     rcx, qword_1803CE250
0x1801dd1ae  mov     cs:qword_1803CEF18, rcx
0x1801dd1b5  cmp     [rcx+8], r13b
0x1801dd1b9  jz      short loc_1801DD1E0
0x1801dd1bb  call    sub_1800402C0
0x1801dd1c0  cmp     [rax+7CCh], ebx
0x1801dd1c6  jz      short loc_1801DD1E0
0x1801dd1c8  mov     r9d, ebx
0x1801dd1cb  lea     rdx, aCmediasessionU_2; "CMediaSession::UpdateOutputTypeGUID"
0x1801dd1d2  mov     r8d, 2568h
0x1801dd1d8  mov     rcx, rax
0x1801dd1db  call    sub_1800EC0E0
0x1801dd1e0  cmp     cs:byte_1803CECE8, 1
0x1801dd1e7  jb      loc_1801DD718
0x1801dd1ed  mov     edx, 2F1h
0x1801dd1f2  jmp     loc_1801DD6FA
0x1801dd1f7  mov     rcx, [rbp+57h+var_68]
0x1801dd1fb  lea     rdx, [rbp+57h+var_70]
0x1801dd1ff  mov     rax, [rcx]
0x1801dd202  mov     rax, [rax+110h]
0x1801dd209  call    cs:__guard_dispatch_icall_fptr
0x1801dd20f  mov     ebx, eax
0x1801dd211  test    eax, eax
0x1801dd213  jns     loc_1801DD2AF
0x1801dd219  mov     rcx, cs:qword_1803CEF18
0x1801dd220  test    rcx, rcx
0x1801dd223  jnz     short loc_1801DD26D
0x1801dd225  call    cs:MFGetCallStackTracingWeakReference
0x1801dd22c  nop     dword ptr [rax+rax+00h]
0x1801dd231  mov     cs:qword_1803CEF18, rax
0x1801dd238  mov     rcx, rax
0x1801dd23b  test    rax, rax
0x1801dd23e  jz      short loc_1801DD25F
0x1801dd240  mov     rax, [rax]
0x1801dd243  mov     edx, 7F0h
0x1801dd248  mov     rax, [rax+8]
0x1801dd24c  call    cs:__guard_dispatch_icall_fptr
0x1801dd252  test    eax, eax
0x1801dd254  jz      short loc_1801DD25F
0x1801dd256  mov     rcx, cs:qword_1803CEF18
0x1801dd25d  jmp     short loc_1801DD26D
0x1801dd25f  lea     rcx, qword_1803CE250
0x1801dd266  mov     cs:qword_1803CEF18, rcx
0x1801dd26d  cmp     [rcx+8], r13b
0x1801dd271  jz      short loc_1801DD298
0x1801dd273  call    sub_1800402C0
0x1801dd278  cmp     [rax+7CCh], ebx
0x1801dd27e  jz      short loc_1801DD298
0x1801dd280  mov     r9d, ebx
0x1801dd283  lea     rdx, aCmediasessionU_2; "CMediaSession::UpdateOutputTypeGUID"
0x1801dd28a  mov     r8d, 2569h
0x1801dd290  mov     rcx, rax
0x1801dd293  call    sub_1800EC0E0
0x1801dd298  cmp     cs:byte_1803CECE8, 1
0x1801dd29f  jb      loc_1801DD718
0x1801dd2a5  mov     edx, 2F2h
0x1801dd2aa  jmp     loc_1801DD6FA
0x1801dd2af  mov     rcx, [rbp+57h+var_70]
0x1801dd2b3  lea     r8, [rbp+57h+var_80]
0x1801dd2b7  lea     rdx, stru_180367B40
0x1801dd2be  mov     rax, [rcx]
0x1801dd2c1  mov     rax, [rax]
0x1801dd2c4  call    cs:__guard_dispatch_icall_fptr
0x1801dd2ca  mov     ebx, eax
0x1801dd2cc  test    eax, eax
0x1801dd2ce  jns     loc_1801DD36A
0x1801dd2d4  mov     rcx, cs:qword_1803CEF18
0x1801dd2db  test    rcx, rcx
0x1801dd2de  jnz     short loc_1801DD328
0x1801dd2e0  call    cs:MFGetCallStackTracingWeakReference
0x1801dd2e7  nop     dword ptr [rax+rax+00h]
0x1801dd2ec  mov     cs:qword_1803CEF18, rax
0x1801dd2f3  mov     rcx, rax
0x1801dd2f6  test    rax, rax
0x1801dd2f9  jz      short loc_1801DD31A
0x1801dd2fb  mov     rax, [rax]
0x1801dd2fe  mov     edx, 7F0h
0x1801dd303  mov     rax, [rax+8]
0x1801dd307  call    cs:__guard_dispatch_icall_fptr
0x1801dd30d  test    eax, eax
0x1801dd30f  jz      short loc_1801DD31A
0x1801dd311  mov     rcx, cs:qword_1803CEF18
0x1801dd318  jmp     short loc_1801DD328
0x1801dd31a  lea     rcx, qword_1803CE250
0x1801dd321  mov     cs:qword_1803CEF18, rcx
0x1801dd328  cmp     [rcx+8], r13b
0x1801dd32c  jz      short loc_1801DD353
0x1801dd32e  call    sub_1800402C0
0x1801dd333  cmp     [rax+7CCh], ebx
0x1801dd339  jz      short loc_1801DD353
0x1801dd33b  mov     r9d, ebx
0x1801dd33e  lea     rdx, aCmediasessionU_2; "CMediaSession::UpdateOutputTypeGUID"
0x1801dd345  mov     r8d, 256Ah
0x1801dd34b  mov     rcx, rax
0x1801dd34e  call    sub_1800EC0E0
0x1801dd353  cmp     cs:byte_1803CECE8, 1
0x1801dd35a  jb      loc_1801DD718
0x1801dd360  mov     edx, 2F3h
0x1801dd365  jmp     loc_1801DD6FA
0x1801dd36a  lea     rcx, [rbp+57h+ppMFType]; ppMFType
0x1801dd36e  call    cs:MFCreateMediaType
0x1801dd375  nop     dword ptr [rax+rax+00h]
0x1801dd37a  mov     ebx, eax
0x1801dd37c  test    eax, eax
0x1801dd37e  jns     loc_1801DD41A
0x1801dd384  mov     rcx, cs:qword_1803CEF18
0x1801dd38b  test    rcx, rcx
0x1801dd38e  jnz     short loc_1801DD3D8
0x1801dd390  call    cs:MFGetCallStackTracingWeakReference
0x1801dd397  nop     dword ptr [rax+rax+00h]
0x1801dd39c  mov     cs:qword_1803CEF18, rax
0x1801dd3a3  mov     rcx, rax
0x1801dd3a6  test    rax, rax
0x1801dd3a9  jz      short loc_1801DD3CA
0x1801dd3ab  mov     rax, [rax]
0x1801dd3ae  mov     edx, 7F0h
0x1801dd3b3  mov     rax, [rax+8]
0x1801dd3b7  call    cs:__guard_dispatch_icall_fptr
0x1801dd3bd  test    eax, eax
0x1801dd3bf  jz      short loc_1801DD3CA
0x1801dd3c1  mov     rcx, cs:qword_1803CEF18
0x1801dd3c8  jmp     short loc_1801DD3D8
0x1801dd3ca  lea     rcx, qword_1803CE250
0x1801dd3d1  mov     cs:qword_1803CEF18, rcx
0x1801dd3d8  cmp     [rcx+8], r13b
0x1801dd3dc  jz      short loc_1801DD403
0x1801dd3de  call    sub_1800402C0
0x1801dd3e3  cmp     [rax+7CCh], ebx
0x1801dd3e9  jz      short loc_1801DD403
0x1801dd3eb  mov     r9d, ebx
0x1801dd3ee  lea     rdx, aCmediasessionU_2; "CMediaSession::UpdateOutputTypeGUID"
0x1801dd3f5  mov     r8d, 256Ch
0x1801dd3fb  mov     rcx, rax
0x1801dd3fe  call    sub_1800EC0E0
0x1801dd403  cmp     cs:byte_1803CECE8, 1
0x1801dd40a  jb      loc_1801DD718
0x1801dd410  mov     edx, 2F4h
0x1801dd415  jmp     loc_1801DD6FA
0x1801dd41a  mov     rcx, [rbp+57h+var_80]
0x1801dd41e  lea     r8, [rbp+57h+var_78]
0x1801dd422  xor     edx, edx
0x1801dd424  mov     rax, [rcx]
0x1801dd427  mov     rax, [rax+90h]
0x1801dd42e  call    cs:__guard_dispatch_icall_fptr
0x1801dd434  mov     ebx, eax
0x1801dd436  test    eax, eax
0x1801dd438  jns     loc_1801DD4D4
0x1801dd43e  mov     rcx, cs:qword_1803CEF18
0x1801dd445  test    rcx, rcx
0x1801dd448  jnz     short loc_1801DD492
0x1801dd44a  call    cs:MFGetCallStackTracingWeakReference
0x1801dd451  nop     dword ptr [rax+rax+00h]
0x1801dd456  mov     cs:qword_1803CEF18, rax
0x1801dd45d  mov     rcx, rax
0x1801dd460  test    rax, rax
0x1801dd463  jz      short loc_1801DD484
0x1801dd465  mov     rax, [rax]
0x1801dd468  mov     edx, 7F0h
0x1801dd46d  mov     rax, [rax+8]
0x1801dd471  call    cs:__guard_dispatch_icall_fptr
0x1801dd477  test    eax, eax
0x1801dd479  jz      short loc_1801DD484
0x1801dd47b  mov     rcx, cs:qword_1803CEF18
0x1801dd482  jmp     short loc_1801DD492
0x1801dd484  lea     rcx, qword_1803CE250
0x1801dd48b  mov     cs:qword_1803CEF18, rcx
0x1801dd492  cmp     [rcx+8], r13b
0x1801dd496  jz      short loc_1801DD4BD
0x1801dd498  call    sub_1800402C0
0x1801dd49d  cmp     [rax+7CCh], ebx
0x1801dd4a3  jz      short loc_1801DD4BD
0x1801dd4a5  mov     r9d, ebx
0x1801dd4a8  lea     rdx, aCmediasessionU_2; "CMediaSession::UpdateOutputTypeGUID"
0x1801dd4af  mov     r8d, 256Dh
0x1801dd4b5  mov     rcx, rax
0x1801dd4b8  call    sub_1800EC0E0
0x1801dd4bd  cmp     cs:byte_1803CECE8, 1
0x1801dd4c4  jb      loc_1801DD718
0x1801dd4ca  mov     edx, 2F5h
0x1801dd4cf  jmp     loc_1801DD6FA
0x1801dd4d4  mov     rcx, [rbp+57h+var_78]
0x1801dd4d8  mov     rdx, [rbp+57h+ppMFType]
0x1801dd4dc  mov     rax, [rcx]
0x1801dd4df  mov     rax, [rax+100h]
0x1801dd4e6  call    cs:__guard_dispatch_icall_fptr
0x1801dd4ec  mov     ebx, eax
0x1801dd4ee  test    eax, eax
0x1801dd4f0  jns     loc_1801DD58C
0x1801dd4f6  mov     rcx, cs:qword_1803CEF18
  ... truncated ...
```
