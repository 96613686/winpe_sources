# CfAbortOperation

- ea: `0x180002630`
- end: `0x180002bf8`
- name: `CfAbortOperation`
- size: `1480`
- prototype: ``
- caller_count: `0`
- callee_count: `5`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callees

- `0x180001a80`
- `0x1800022ee`
- `0x180002630`
- `0x180011338`
- `0x180011e18`

## import_xrefs

- `ntdll!RtlNtStatusToDosError` at `0x180002735`
- `ntdll!RtlNtStatusToDosError` at `0x1800027c1`
- `ntdll!RtlNtStatusToDosError` at `0x18000284f`
- `ntdll!RtlNtStatusToDosError` at `0x1800028de`
- `ntdll!RtlNtStatusToDosError` at `0x18000296d`
- `ntdll!RtlNtStatusToDosError` at `0x1800029fc`
- `ntdll!RtlNtStatusToDosError` at `0x180002a81`
- `ntdll!RtlNtStatusToDosError` at `0x180002b04`
- `ntdll!RtlNtStatusToDosError` at `0x180002735`
- `ntdll!RtlNtStatusToDosError` at `0x1800027c1`
- `ntdll!RtlNtStatusToDosError` at `0x18000284f`
- `ntdll!RtlNtStatusToDosError` at `0x1800028de`
- `ntdll!RtlNtStatusToDosError` at `0x18000296d`
- `ntdll!RtlNtStatusToDosError` at `0x1800029fc`
- `ntdll!RtlNtStatusToDosError` at `0x180002a81`
- `ntdll!RtlNtStatusToDosError` at `0x180002b04`
- `api-ms-win-core-realtime-l1-1-0!QueryUnbiasedInterruptTime` at `0x1800026a6`
- `api-ms-win-core-realtime-l1-1-0!QueryUnbiasedInterruptTime` at `0x1800026a6`
- `FLTLIB!FilterSendMessage` at `0x180002b55`
- `FLTLIB!FilterSendMessage` at `0x180002b55`

## string_xrefs

- `0x1800027db`: `SetCldMsgCommand Failed`
- `0x180002a9b`: `SetCldDsMsgProcessId Failed`

## pseudocode

```c
__int64 __fastcall CfAbortOperation(int a1, __int64 *a2, int a3)
{
  int v6; // ebx
  const wchar_t *v7; // rcx
  NTSTATUS v8; // esi
  NTSTATUS v9; // ecx
  DWORD v10; // ecx
  signed int v11; // eax
  NTSTATUS v12; // ecx
  DWORD v13; // ecx
  __int64 v14; // rax
  signed int v15; // eax
  __int64 v16; // rdx
  NTSTATUS v17; // ecx
  __int64 v18; // rax
  signed int v19; // eax
  __int64 v20; // rdx
  NTSTATUS v21; // ecx
  __int64 v22; // rax
  signed int v23; // eax
  __int64 v24; // rdx
  NTSTATUS v25; // ecx
  __int64 v26; // rax
  signed int v27; // eax
  __int64 v28; // rdx
  NTSTATUS v29; // ecx
  __int64 v30; // rax
  signed int v31; // eax
  NTSTATUS v32; // ecx
  __int64 v33; // rax
  signed int v34; // eax
  __int64 v35; // rax
  signed int v36; // eax
  HRESULT v37; // eax
  DWORD BytesReturned; // [rsp+40h] [rbp-C0h] BYREF
  unsigned __int64 UnbiasedTime; // [rsp+48h] [rbp-B8h] BYREF
  int v41; // [rsp+50h] [rbp-B0h] BYREF
  const wchar_t *v42; // [rsp+58h] [rbp-A8h]
  int v43; // [rsp+60h] [rbp-A0h]
  int v44; // [rsp+64h] [rbp-9Ch]
  __int64 v45; // [rsp+68h] [rbp-98h]
  __int64 v46; // [rsp+70h] [rbp-90h]
  __int64 InBuffer; // [rsp+B0h] [rbp-50h] BYREF
  DWORD dwInBufferSize; // [rsp+B8h] [rbp-48h]
  int v49; // [rsp+BCh] [rbp-44h]
  _DWORD v50[2]; // [rsp+C0h] [rbp-40h] BYREF
  int v51; // [rsp+C8h] [rbp-38h]
  unsigned int v52; // [rsp+CCh] [rbp-34h]
  int v53; // [rsp+E0h] [rbp-20h]
  int v54; // [rsp+E4h] [rbp-1Ch]
  int v55; // [rsp+E8h] [rbp-18h]
  int v56; // [rsp+ECh] [rbp-14h]
  int v57; // [rsp+F8h] [rbp-8h]
  int v58; // [rsp+FCh] [rbp-4h]
  int v59; // [rsp+120h] [rbp+20h]
  int v60; // [rsp+124h] [rbp+24h]
  int v61; // [rsp+128h] [rbp+28h]
  int v62; // [rsp+12Ch] [rbp+2Ch]
  int v63; // [rsp+130h] [rbp+30h]
  int v64; // [rsp+134h] [rbp+34h]

  BytesReturned = 0;
  memset_0(&v41, 0, 0x58u);
  UnbiasedTime = 0;
  v6 = GlobalPortInit(0);
  if ( v6 > -1 )
  {
    QueryUnbiasedInterruptTime(&UnbiasedTime);
    memset_0(v50, 0, 0xF0u);
    InBuffer = 1886219331;
    dwInBufferSize = 200;
    v49 = 1507328;
    memset_0(v50, 0, 0xB8u);
    v8 = -1073741811;
    if ( HIWORD(v49) )
    {
      v10 = dwInBufferSize;
      if ( ((dwInBufferSize + 3LL) & 0xFFFFFFFFFFFFFFFCuLL) + 1 <= 0xF8 )
      {
        v50[0] = 65543;
        dwInBufferSize = (dwInBufferSize + 3) & 0xFFFFFFFC;
        v50[1] = (v10 + 3) & 0xFFFFFFFC;
        v9 = 0;
        *((_BYTE *)&InBuffer + dwInBufferSize++) = 1;
      }
      else
      {
        v9 = -1073741789;
      }
    }
    else
    {
      v9 = -1073741811;
    }
    v11 = RtlNtStatusToDosError(v9);
    v6 = v11;
    if ( v11 > 0 )
      v6 = (unsigned __int16)v11 | 0x80070000;
    if ( v6 > -1 )
    {
      if ( HIWORD(v49) > 1u )
      {
        v13 = dwInBufferSize;
        if ( ((dwInBufferSize + 3LL) & 0xFFFFFFFFFFFFFFFCuLL) + 2 <= 0xF8 )
        {
          v14 = (dwInBufferSize + 3) & 0xFFFFFFFC;
          dwInBufferSize = (dwInBufferSize + 3) & 0xFFFFFFFC;
          if ( (_WORD)v51 )
            LOWORD(v49) = v49 | 1;
          v51 = 131080;
          v52 = (v13 + 3) & 0xFFFFFFFC;
          *(_WORD *)((char *)&InBuffer + v14) = 16386;
          v12 = 0;
          dwInBufferSize += 2;
        }
        else
        {
          v12 = -1073741789;
        }
      }
      else
      {
        v12 = -1073741811;
      }
      v15 = RtlNtStatusToDosError(v12);
      v6 = v15;
      if ( v15 > 0 )
        v6 = (unsigned __int16)v15 | 0x80070000;
      if ( v6 > -1 )
      {
        if ( a2 )
          v16 = *a2;
        else
          v16 = 0;
        if ( HIWORD(v49) > 0xDu )
        {
          if ( ((dwInBufferSize + 3LL) & 0xFFFFFFFFFFFFFFFCuLL) + 8 <= 0xF8 )
          {
            v18 = (dwInBufferSize + 3) & 0xFFFFFFFC;
            dwInBufferSize = (dwInBufferSize + 3) & 0xFFFFFFFC;
            if ( (_WORD)v61 )
              LOWORD(v49) = v49 | 1;
            v61 = 524294;
            v17 = 0;
            v62 = v18;
            *(__int64 *)((char *)&InBuffer + v18) = v16;
            dwInBufferSize += 8;
          }
          else
          {
            v17 = -1073741789;
          }
        }
        else
        {
          v17 = -1073741811;
        }
        v19 = RtlNtStatusToDosError(v17);
        v6 = v19;
        if ( v19 > 0 )
          v6 = (unsigned __int16)v19 | 0x80070000;
        if ( v6 > -1 )
        {
          if ( a2 )
            v20 = a2[1];
          else
            v20 = 0;
          if ( HIWORD(v49) > 4u )
          {
            if ( ((dwInBufferSize + 3LL) & 0xFFFFFFFFFFFFFFFCuLL) + 8 <= 0xF8 )
            {
              v22 = (dwInBufferSize + 3) & 0xFFFFFFFC;
              dwInBufferSize = (dwInBufferSize + 3) & 0xFFFFFFFC;
              if ( (_WORD)v53 )
                LOWORD(v49) = v49 | 1;
              v53 = 524294;
              v21 = 0;
              v54 = v22;
              *(__int64 *)((char *)&InBuffer + v22) = v20;
              dwInBufferSize += 8;
            }
            else
            {
              v21 = -1073741789;
            }
          }
          else
          {
            v21 = -1073741811;
          }
          v23 = RtlNtStatusToDosError(v21);
          v6 = v23;
          if ( v23 > 0 )
            v6 = (unsigned __int16)v23 | 0x80070000;
          if ( v6 > -1 )
          {
            if ( a2 )
              v24 = a2[2];
            else
              v24 = 0;
            if ( HIWORD(v49) > 7u )
            {
              if ( ((dwInBufferSize + 3LL) & 0xFFFFFFFFFFFFFFFCuLL) + 8 <= 0xF8 )
              {
                v26 = (dwInBufferSize + 3) & 0xFFFFFFFC;
                dwInBufferSize = (dwInBufferSize + 3) & 0xFFFFFFFC;
                if ( (_WORD)v57 )
                  LOWORD(v49) = v49 | 1;
                v57 = 524294;
                v25 = 0;
                v58 = v26;
                *(__int64 *)((char *)&InBuffer + v26) = v24;
                dwInBufferSize += 8;
              }
              else
              {
                v25 = -1073741789;
              }
            }
            else
            {
              v25 = -1073741811;
            }
            v27 = RtlNtStatusToDosError(v25);
            v6 = v27;
            if ( v27 > 0 )
              v6 = (unsigned __int16)v27 | 0x80070000;
            if ( v6 > -1 )
            {
              if ( a2 )
                v28 = a2[3];
              else
                v28 = 0;
              if ( HIWORD(v49) > 0xCu )
              {
                if ( ((dwInBufferSize + 3LL) & 0xFFFFFFFFFFFFFFFCuLL) + 8 <= 0xF8 )
                {
                  v30 = (dwInBufferSize + 3) & 0xFFFFFFFC;
                  dwInBufferSize = (dwInBufferSize + 3) & 0xFFFFFFFC;
                  if ( (_WORD)v59 )
                    LOWORD(v49) = v49 | 1;
                  v59 = 524294;
                  v29 = 0;
                  v60 = v30;
                  *(__int64 *)((char *)&InBuffer + v30) = v28;
                  dwInBufferSize += 8;
                }
                else
                {
                  v29 = -1073741789;
                }
              }
              else
              {
                v29 = -1073741811;
              }
              v31 = RtlNtStatusToDosError(v29);
              v6 = v31;
              if ( v31 > 0 )
                v6 = (unsigned __int16)v31 | 0x80070000;
              if ( v6 > -1 )
              {
                if ( HIWORD(v49) > 0xEu )
                {
                  if ( ((dwInBufferSize + 3LL) & 0xFFFFFFFFFFFFFFFCuLL) + 4 <= 0xF8 )
                  {
                    v33 = (dwInBufferSize + 3) & 0xFFFFFFFC;
                    dwInBufferSize = (dwInBufferSize + 3) & 0xFFFFFFFC;
                    if ( (_WORD)v63 )
                      LOWORD(v49) = v49 | 1;
                    v63 = 262154;
                    v32 = 0;
                    v64 = v33;
                    *(_DWORD *)((char *)&InBuffer + v33) = a1;
                    dwInBufferSize += 4;
                  }
                  else
                  {
                    v32 = -1073741789;
                  }
                }
                else
                {
                  v32 = -1073741811;
                }
                v34 = RtlNtStatusToDosError(v32);
                v6 = v34;
                if ( v34 > 0 )
                  v6 = (unsigned __int16)v34 | 0x80070000;
                if ( v6 > -1 )
                {
                  if ( HIWORD(v49) > 5u )
                  {
                    if ( ((dwInBufferSize + 3LL) & 0xFFFFFFFFFFFFFFFCuLL) + 4 <= 0xF8 )
                    {
                      v35 = (dwInBufferSize + 3) & 0xFFFFFFFC;
                      dwInBufferSize = (dwInBufferSize + 3) & 0xFFFFFFFC;
                      if ( (_WORD)v55 )
                        LOWORD(v49) = v49 | 1;
                      v55 = 262154;
                      v8 = 0;
                      v56 = v35;
                      *(_DWORD *)((char *)&InBuffer + v35) = a3;
                      dwInBufferSize += 4;
                    }
                    else
                    {
                      v8 = -1073741789;
                    }
                  }
                  v36 = RtlNtStatusToDosError(v8);
                  v6 = v36;
                  if ( v36 > 0 )
                    v6 = (unsigned __int16)v36 | 0x80070000;
                  if ( v6 > -1 )
                  {
                    LOWORD(v49) = v49 & 0xFFFD;
                    HIDWORD(InBuffer) = 0;
                    v37 = FilterSendMessage(hPort, &InBuffer, dwInBufferSize, 0, 0, &BytesReturned);
                    v7 = L"FilterSendMessage failed";
                    v6 = v37;
                    if ( v37 > -1 )
                      v7 = 0;
                  }
                  else
                  {
                    v7 = L"SetCldDsMsgFlags Failed";
                  }
                }
                else
                {
                  v7 = L"SetCldDsMsgProcessId Failed";
                }
              }
              else
              {
                v7 = L"SetCldDsMsgRequestKey Failed";
              }
            }
            else
            {
              v7 = L"SetCldDsMsgStreamKey Failed";
            }
          }
          else
          {
            v7 = L"SetCldDsMsgSyncRootKey Failed";
          }
        }
        else
        {
          v7 = L"SetCldDsMsgProviderKey Failed";
        }
      }
      else
      {
        v7 = L"SetCldMsgCommand Failed";
      }
    }
    else
    {
      v7 = L"SetVersion Failed";
    }
  }
  else
  {
    v7 = L"GlobalPortInit Failed";
  }
  v42 = v7;
  v44 = a3;
  v43 = a1;
  if ( a2 )
  {
    v45 = a2[1];
    v46 = a2[2];
  }
  else
  {
    v45 = 0;
    v46 = 0;
  }
  TlmLogApiReliability(0x15u, 0, 0, 0, 0, UnbiasedTime, &v41, v6);
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x180002630  mov     [rsp-8+arg_18], rbx
0x180002635  push    rbp
0x180002636  push    rsi
0x180002637  push    rdi
0x180002638  push    r12
0x18000263a  push    r13
0x18000263c  push    r14
0x18000263e  push    r15
0x180002640  lea     rbp, [rsp-0C0h]
0x180002648  sub     rsp, 1C0h
0x18000264f  mov     rax, cs:__security_cookie
0x180002656  xor     rax, rsp
0x180002659  mov     [rbp+0F0h+var_40], rax
0x180002660  xor     r12d, r12d
0x180002663  mov     r14d, r8d
0x180002666  mov     rdi, rdx
0x180002669  mov     [rsp+1F0h+BytesReturned], r12d
0x18000266e  mov     r15d, ecx
0x180002671  xor     edx, edx; Val
0x180002673  lea     rcx, [rsp+1F0h+var_1A0]; void *
0x180002678  lea     r8d, [r12+58h]; Size
0x18000267d  call    memset_0
0x180002682  xor     ecx, ecx
0x180002684  mov     [rsp+1F0h+UnbiasedTime], r12
0x180002689  call    GlobalPortInit
0x18000268e  mov     ebx, eax
0x180002690  cmp     eax, 0FFFFFFFFh
0x180002693  jg      short loc_1800026A1
0x180002695  lea     rcx, aGlobalportinit; "GlobalPortInit Failed"
0x18000269c  jmp     loc_180002B6B
0x1800026a1  lea     rcx, [rsp+1F0h+UnbiasedTime]; UnbiasedTime
0x1800026a6  call    cs:__imp_QueryUnbiasedInterruptTime
0x1800026ac  xor     edx, edx; Val
0x1800026ae  lea     rcx, [rbp+0F0h+var_130]; void *
0x1800026b2  mov     r8d, 0F0h; Size
0x1800026b8  call    memset_0
0x1800026bd  xor     edx, edx; Val
0x1800026bf  mov     [rbp+0F0h+InBuffer], 706D6C43h
0x1800026c7  mov     r8d, 0B8h; Size
0x1800026cd  mov     [rbp+0F0h+dwInBufferSize], 0C8h
0x1800026d4  lea     rcx, [rbp+0F0h+var_130]; void *
0x1800026d8  mov     [rbp+0F0h+var_134], 170000h
0x1800026df  call    memset_0
0x1800026e4  mov     edx, 1
0x1800026e9  mov     esi, 0C000000Dh
0x1800026ee  cmp     r12w, word ptr [rbp+0F0h+var_134+2]
0x1800026f3  jb      short loc_1800026F9
0x1800026f5  mov     ecx, esi
0x1800026f7  jmp     short loc_180002735
0x1800026f9  mov     ecx, [rbp+0F0h+dwInBufferSize]
0x1800026fc  lea     rax, [rcx+3]
0x180002700  and     rax, 0FFFFFFFFFFFFFFFCh
0x180002704  add     rax, rdx
0x180002707  cmp     rax, 0F8h
0x18000270d  jbe     short loc_180002716
0x18000270f  mov     ecx, 0C0000023h
0x180002714  jmp     short loc_180002735
0x180002716  lea     eax, [rcx+3]
0x180002719  mov     [rbp+0F0h+var_130], 10007h
0x180002720  and     eax, 0FFFFFFFCh
0x180002723  mov     ecx, eax
0x180002725  mov     [rbp+0F0h+dwInBufferSize], ecx
0x180002728  mov     [rbp+0F0h+var_12C], ecx
0x18000272b  mov     ecx, r12d; Status
0x18000272e  mov     byte ptr [rbp+rax+0F0h+InBuffer], dl
0x180002732  add     [rbp+0F0h+dwInBufferSize], edx
0x180002735  call    cs:__imp_RtlNtStatusToDosError
0x18000273b  mov     ebx, eax
0x18000273d  test    eax, eax
0x18000273f  jle     short loc_18000274A
0x180002741  movzx   ebx, ax
0x180002744  or      ebx, 80070000h
0x18000274a  cmp     ebx, 0FFFFFFFFh
0x18000274d  jg      short loc_18000275B
0x18000274f  lea     rcx, aSetversionFail_0; "SetVersion Failed"
0x180002756  jmp     loc_180002B6B
0x18000275b  mov     r13d, 8
0x180002761  lea     r8d, [r13-7]
0x180002765  cmp     r8w, word ptr [rbp+0F0h+var_134+2]
0x18000276a  jb      short loc_180002770
0x18000276c  mov     ecx, esi
0x18000276e  jmp     short loc_1800027C1
0x180002770  mov     ecx, [rbp+0F0h+dwInBufferSize]
0x180002773  mov     edx, 2
0x180002778  lea     rax, [rcx+3]
0x18000277c  and     rax, 0FFFFFFFFFFFFFFFCh
0x180002780  add     rax, rdx
0x180002783  cmp     rax, 0F8h
0x180002789  jbe     short loc_180002792
0x18000278b  mov     ecx, 0C0000023h
0x180002790  jmp     short loc_1800027C1
0x180002792  lea     eax, [rcx+3]
0x180002795  and     eax, 0FFFFFFFCh
0x180002798  mov     [rbp+0F0h+dwInBufferSize], eax
0x18000279b  cmp     word ptr [rbp+0F0h+var_128], r12w
0x1800027a0  jz      short loc_1800027A7
0x1800027a2  or      word ptr [rbp+0F0h+var_134], r8w
0x1800027a7  mov     ecx, 4002h
0x1800027ac  mov     [rbp+0F0h+var_128], 20008h
0x1800027b3  mov     [rbp+0F0h+var_124], eax
0x1800027b6  mov     word ptr [rbp+rax+0F0h+InBuffer], cx
0x1800027bb  mov     ecx, r12d; Status
0x1800027be  add     [rbp+0F0h+dwInBufferSize], edx
0x1800027c1  call    cs:__imp_RtlNtStatusToDosError
0x1800027c7  mov     ebx, eax
0x1800027c9  test    eax, eax
0x1800027cb  jle     short loc_1800027D6
0x1800027cd  movzx   ebx, ax
0x1800027d0  or      ebx, 80070000h
0x1800027d6  cmp     ebx, 0FFFFFFFFh
0x1800027d9  jg      short loc_1800027E7
0x1800027db  lea     rcx, aSetcldmsgcomma_0; "SetCldMsgCommand Failed"
0x1800027e2  jmp     loc_180002B6B
0x1800027e7  test    rdi, rdi
0x1800027ea  jz      short loc_1800027F1
0x1800027ec  mov     rdx, [rdi]
0x1800027ef  jmp     short loc_1800027F4
0x1800027f1  mov     rdx, r12
0x1800027f4  mov     eax, 0Dh
0x1800027f9  cmp     ax, word ptr [rbp+0F0h+var_134+2]
0x1800027fd  jb      short loc_180002803
0x1800027ff  mov     ecx, esi
0x180002801  jmp     short loc_18000284F
0x180002803  mov     ecx, [rbp+0F0h+dwInBufferSize]
0x180002806  lea     rax, [rcx+3]
0x18000280a  and     rax, 0FFFFFFFFFFFFFFFCh
0x18000280e  add     rax, r13
0x180002811  cmp     rax, 0F8h
0x180002817  jbe     short loc_180002820
0x180002819  mov     ecx, 0C0000023h
0x18000281e  jmp     short loc_18000284F
0x180002820  lea     eax, [rcx+3]
0x180002823  and     eax, 0FFFFFFFCh
0x180002826  mov     [rbp+0F0h+dwInBufferSize], eax
0x180002829  cmp     word ptr [rbp+0F0h+var_C8], r12w
0x18000282e  jz      short loc_180002839
0x180002830  mov     ecx, 1
0x180002835  or      word ptr [rbp+0F0h+var_134], cx
0x180002839  mov     [rbp+0F0h+var_C8], 80006h
0x180002840  mov     ecx, r12d; Status
0x180002843  mov     [rbp+0F0h+var_C4], eax
0x180002846  mov     [rbp+rax+0F0h+InBuffer], rdx
0x18000284b  add     [rbp+0F0h+dwInBufferSize], r13d
0x18000284f  call    cs:__imp_RtlNtStatusToDosError
0x180002855  mov     ebx, eax
0x180002857  test    eax, eax
0x180002859  jle     short loc_180002864
0x18000285b  movzx   ebx, ax
0x18000285e  or      ebx, 80070000h
0x180002864  cmp     ebx, 0FFFFFFFFh
0x180002867  jg      short loc_180002875
0x180002869  lea     rcx, aSetclddsmsgpro_0; "SetCldDsMsgProviderKey Failed"
0x180002870  jmp     loc_180002B6B
0x180002875  test    rdi, rdi
0x180002878  jz      short loc_180002880
0x18000287a  mov     rdx, [rdi+8]
0x18000287e  jmp     short loc_180002883
0x180002880  mov     rdx, r12
0x180002883  mov     eax, 4
0x180002888  cmp     ax, word ptr [rbp+0F0h+var_134+2]
0x18000288c  jb      short loc_180002892
0x18000288e  mov     ecx, esi
0x180002890  jmp     short loc_1800028DE
0x180002892  mov     ecx, [rbp+0F0h+dwInBufferSize]
0x180002895  lea     rax, [rcx+3]
0x180002899  and     rax, 0FFFFFFFFFFFFFFFCh
0x18000289d  add     rax, r13
0x1800028a0  cmp     rax, 0F8h
0x1800028a6  jbe     short loc_1800028AF
0x1800028a8  mov     ecx, 0C0000023h
0x1800028ad  jmp     short loc_1800028DE
0x1800028af  lea     eax, [rcx+3]
0x1800028b2  and     eax, 0FFFFFFFCh
0x1800028b5  mov     [rbp+0F0h+dwInBufferSize], eax
0x1800028b8  cmp     word ptr [rbp+0F0h+var_110], r12w
0x1800028bd  jz      short loc_1800028C8
0x1800028bf  mov     ecx, 1
0x1800028c4  or      word ptr [rbp+0F0h+var_134], cx
0x1800028c8  mov     [rbp+0F0h+var_110], 80006h
0x1800028cf  mov     ecx, r12d; Status
0x1800028d2  mov     [rbp+0F0h+var_10C], eax
0x1800028d5  mov     [rbp+rax+0F0h+InBuffer], rdx
0x1800028da  add     [rbp+0F0h+dwInBufferSize], r13d
0x1800028de  call    cs:__imp_RtlNtStatusToDosError
0x1800028e4  mov     ebx, eax
0x1800028e6  test    eax, eax
0x1800028e8  jle     short loc_1800028F3
0x1800028ea  movzx   ebx, ax
0x1800028ed  or      ebx, 80070000h
0x1800028f3  cmp     ebx, 0FFFFFFFFh
0x1800028f6  jg      short loc_180002904
0x1800028f8  lea     rcx, aSetclddsmsgsyn; "SetCldDsMsgSyncRootKey Failed"
0x1800028ff  jmp     loc_180002B6B
0x180002904  test    rdi, rdi
0x180002907  jz      short loc_18000290F
0x180002909  mov     rdx, [rdi+10h]
0x18000290d  jmp     short loc_180002912
0x18000290f  mov     rdx, r12
0x180002912  mov     eax, 7
0x180002917  cmp     ax, word ptr [rbp+0F0h+var_134+2]
0x18000291b  jb      short loc_180002921
0x18000291d  mov     ecx, esi
0x18000291f  jmp     short loc_18000296D
0x180002921  mov     ecx, [rbp+0F0h+dwInBufferSize]
0x180002924  lea     rax, [rcx+3]
0x180002928  and     rax, 0FFFFFFFFFFFFFFFCh
0x18000292c  add     rax, r13
0x18000292f  cmp     rax, 0F8h
0x180002935  jbe     short loc_18000293E
0x180002937  mov     ecx, 0C0000023h
0x18000293c  jmp     short loc_18000296D
0x18000293e  lea     eax, [rcx+3]
0x180002941  and     eax, 0FFFFFFFCh
0x180002944  mov     [rbp+0F0h+dwInBufferSize], eax
0x180002947  cmp     word ptr [rbp+0F0h+var_F8], r12w
0x18000294c  jz      short loc_180002957
0x18000294e  mov     ecx, 1
0x180002953  or      word ptr [rbp+0F0h+var_134], cx
0x180002957  mov     [rbp+0F0h+var_F8], 80006h
0x18000295e  mov     ecx, r12d; Status
0x180002961  mov     [rbp+0F0h+var_F4], eax
0x180002964  mov     [rbp+rax+0F0h+InBuffer], rdx
0x180002969  add     [rbp+0F0h+dwInBufferSize], r13d
0x18000296d  call    cs:__imp_RtlNtStatusToDosError
0x180002973  mov     ebx, eax
0x180002975  test    eax, eax
0x180002977  jle     short loc_180002982
0x180002979  movzx   ebx, ax
0x18000297c  or      ebx, 80070000h
0x180002982  cmp     ebx, 0FFFFFFFFh
0x180002985  jg      short loc_180002993
0x180002987  lea     rcx, aSetclddsmsgstr; "SetCldDsMsgStreamKey Failed"
0x18000298e  jmp     loc_180002B6B
0x180002993  test    rdi, rdi
0x180002996  jz      short loc_18000299E
0x180002998  mov     rdx, [rdi+18h]
0x18000299c  jmp     short loc_1800029A1
0x18000299e  mov     rdx, r12
0x1800029a1  mov     eax, 0Ch
0x1800029a6  cmp     ax, word ptr [rbp+0F0h+var_134+2]
0x1800029aa  jb      short loc_1800029B0
0x1800029ac  mov     ecx, esi
0x1800029ae  jmp     short loc_1800029FC
0x1800029b0  mov     ecx, [rbp+0F0h+dwInBufferSize]
0x1800029b3  lea     rax, [rcx+3]
0x1800029b7  and     rax, 0FFFFFFFFFFFFFFFCh
0x1800029bb  add     rax, r13
0x1800029be  cmp     rax, 0F8h
0x1800029c4  jbe     short loc_1800029CD
0x1800029c6  mov     ecx, 0C0000023h
0x1800029cb  jmp     short loc_1800029FC
0x1800029cd  lea     eax, [rcx+3]
0x1800029d0  and     eax, 0FFFFFFFCh
0x1800029d3  mov     [rbp+0F0h+dwInBufferSize], eax
0x1800029d6  cmp     word ptr [rbp+0F0h+var_D0], r12w
0x1800029db  jz      short loc_1800029E6
0x1800029dd  mov     ecx, 1
0x1800029e2  or      word ptr [rbp+0F0h+var_134], cx
0x1800029e6  mov     [rbp+0F0h+var_D0], 80006h
0x1800029ed  mov     ecx, r12d; Status
0x1800029f0  mov     [rbp+0F0h+var_CC], eax
0x1800029f3  mov     [rbp+rax+0F0h+InBuffer], rdx
0x1800029f8  add     [rbp+0F0h+dwInBufferSize], r13d
0x1800029fc  call    cs:__imp_RtlNtStatusToDosError
0x180002a02  mov     ebx, eax
0x180002a04  test    eax, eax
0x180002a06  jle     short loc_180002A11
0x180002a08  movzx   ebx, ax
0x180002a0b  or      ebx, 80070000h
0x180002a11  cmp     ebx, 0FFFFFFFFh
0x180002a14  jg      short loc_180002A22
0x180002a16  lea     rcx, aSetclddsmsgreq; "SetCldDsMsgRequestKey Failed"
0x180002a1d  jmp     loc_180002B6B
0x180002a22  mov     eax, 0Eh
0x180002a27  cmp     ax, word ptr [rbp+0F0h+var_134+2]
0x180002a2b  jb      short loc_180002A31
0x180002a2d  mov     ecx, esi
0x180002a2f  jmp     short loc_180002A81
0x180002a31  mov     ecx, [rbp+0F0h+dwInBufferSize]
0x180002a34  mov     edx, 4
0x180002a39  lea     rax, [rcx+3]
0x180002a3d  and     rax, 0FFFFFFFFFFFFFFFCh
0x180002a41  add     rax, rdx
0x180002a44  cmp     rax, 0F8h
0x180002a4a  jbe     short loc_180002A53
0x180002a4c  mov     ecx, 0C0000023h
0x180002a51  jmp     short loc_180002A81
0x180002a53  lea     eax, [rcx+3]
0x180002a56  and     eax, 0FFFFFFFCh
0x180002a59  mov     [rbp+0F0h+dwInBufferSize], eax
0x180002a5c  cmp     word ptr [rbp+0F0h+var_C0], r12w
0x180002a61  jz      short loc_180002A6C
0x180002a63  mov     ecx, 1
0x180002a68  or      word ptr [rbp+0F0h+var_134], cx
0x180002a6c  mov     [rbp+0F0h+var_C0], 4000Ah
0x180002a73  mov     ecx, r12d; Status
0x180002a76  mov     [rbp+0F0h+var_BC], eax
0x180002a79  mov     dword ptr [rbp+rax+0F0h+InBuffer], r15d
0x180002a7e  add     [rbp+0F0h+dwInBufferSize], edx
0x180002a81  call    cs:__imp_RtlNtStatusToDosError
  ... truncated ...
```
