# CDiagnosticLogNode::GetChildNodeNames(ulong *,ushort * * *)

- ea: `0x180006f60`
- end: `0x1800073ae`
- name: `?GetChildNodeNames@CDiagnosticLogNode@@UEAAJPEAKPEAPEAPEAG@Z`
- size: `1102`
- prototype: `__int64 __fastcall(CDiagnosticLogNode *__hidden this, unsigned int *, unsigned __int16 ***)`
- caller_count: `0`
- callee_count: `2`
- tags: `registry_config, service_task, broker_com_uri`

## callees

- `0x18000108c`
- `0x180006f60`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180006fee`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180007088`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800070f7`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180007176`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180007200`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800072a3`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180006fee`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180007088`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800070f7`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180007176`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180007200`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800072a3`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000705b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180007387`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000705b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180007387`
- `OLEAUT32!__imp_SysAllocString` at `0x180007016`
- `OLEAUT32!__imp_SysAllocString` at `0x1800070ac`
- `OLEAUT32!__imp_SysAllocString` at `0x180007123`
- `OLEAUT32!__imp_SysAllocString` at `0x1800071a2`
- `OLEAUT32!__imp_SysAllocString` at `0x180007228`
- `OLEAUT32!__imp_SysAllocString` at `0x1800072cb`
- `OLEAUT32!__imp_SysAllocString` at `0x180007016`
- `OLEAUT32!__imp_SysAllocString` at `0x1800070ac`
- `OLEAUT32!__imp_SysAllocString` at `0x180007123`
- `OLEAUT32!__imp_SysAllocString` at `0x1800071a2`
- `OLEAUT32!__imp_SysAllocString` at `0x180007228`
- `OLEAUT32!__imp_SysAllocString` at `0x1800072cb`
- `OLEAUT32!__imp_SysFreeString` at `0x18000704c`
- `OLEAUT32!__imp_SysFreeString` at `0x1800070d4`
- `OLEAUT32!__imp_SysFreeString` at `0x180007153`
- `OLEAUT32!__imp_SysFreeString` at `0x1800071d2`
- `OLEAUT32!__imp_SysFreeString` at `0x180007254`
- `OLEAUT32!__imp_SysFreeString` at `0x1800072f7`
- `OLEAUT32!__imp_SysFreeString` at `0x180007377`
- `OLEAUT32!__imp_SysFreeString` at `0x18000704c`
- `OLEAUT32!__imp_SysFreeString` at `0x1800070d4`
- `OLEAUT32!__imp_SysFreeString` at `0x180007153`
- `OLEAUT32!__imp_SysFreeString` at `0x1800071d2`
- `OLEAUT32!__imp_SysFreeString` at `0x180007254`
- `OLEAUT32!__imp_SysFreeString` at `0x1800072f7`
- `OLEAUT32!__imp_SysFreeString` at `0x180007377`

## string_xrefs

- `0x180007164`: `MdmConfiguration`

## pseudocode

```c
__int64 __fastcall CDiagnosticLogNode::GetChildNodeNames(
        __int64 this,
        unsigned int *a2,
        unsigned __int16 ***a3,
        __int64 a4)
{
  int v6; // ecx
  int v7; // ecx
  int v8; // ecx
  int v9; // ecx
  unsigned int v10; // ebx
  __int64 v11; // rbx
  unsigned __int16 **v12; // rax
  unsigned __int16 **v13; // rsi
  unsigned int v14; // edi
  int v15; // r14d
  BSTR v16; // rax
  unsigned int i; // ebx
  __int64 v18; // rbx
  unsigned __int16 **v19; // rax
  BSTR v20; // rax
  unsigned int j; // ebx
  __int64 v22; // rbx
  unsigned __int16 **v23; // rax
  int v24; // r14d
  BSTR v25; // rax
  unsigned int k; // ebx
  __int64 v27; // rbx
  unsigned __int16 **v28; // rax
  int v29; // r14d
  BSTR v30; // rax
  unsigned int m; // ebx
  __int64 v32; // rbx
  unsigned __int16 **v33; // rax
  BSTR v34; // rax
  unsigned int n; // ebx
  __int64 v36; // rbx
  unsigned __int16 **v37; // rax
  BSTR v38; // rax
  unsigned int ii; // ebx
  int v40; // eax
  BSTR *v41; // rdi
  unsigned int v42; // r14d
  unsigned int jj; // esi
  OLECHAR *v45; // [rsp+30h] [rbp-40h]
  const wchar_t *v46; // [rsp+38h] [rbp-38h]
  OLECHAR *v47[6]; // [rsp+40h] [rbp-30h]
  OLECHAR *psz; // [rsp+B8h] [rbp+48h] BYREF
  int v49; // [rsp+C8h] [rbp+58h] BYREF

  if ( a2 && a3 )
  {
    *a2 = 0;
    *a3 = 0;
    v6 = *(_DWORD *)(this + 44);
    if ( v6 )
    {
      v7 = v6 - 1;
      if ( v7 )
      {
        v8 = v7 - 17;
        if ( v8 )
        {
          v9 = v8 - 2;
          if ( v9 )
          {
            this = (unsigned int)(v9 - 9);
            if ( (_DWORD)this )
            {
              if ( (_DWORD)this != 3 )
              {
                *a2 = 0;
                *a3 = 0;
                v10 = -2046820335;
                goto LABEL_69;
              }
              v11 = 8;
              psz = L"Channels";
              v12 = (unsigned __int16 **)CoTaskMemAlloc(8u);
              v13 = v12;
              if ( !v12 )
                goto LABEL_20;
              v14 = 0;
              do
              {
                *(_BYTE *)v12 = 0;
                v12 = (unsigned __int16 **)((char *)v12 + 1);
                --v11;
              }
              while ( v11 );
              v15 = 0;
              while ( 1 )
              {
                v16 = SysAllocString((&psz)[v15]);
                v13[v15] = v16;
                if ( !v16 )
                  break;
                ++v14;
                if ( ++v15 )
                  goto LABEL_16;
              }
              for ( i = 0; i < v14; ++i )
                SysFreeString(v13[i]);
            }
            else
            {
              v18 = 16;
              v45 = L"ArchiveDefinition";
              v46 = L"ArchiveResults";
              v19 = (unsigned __int16 **)CoTaskMemAlloc(0x10u);
              v13 = v19;
              if ( !v19 )
                goto LABEL_20;
              v14 = 0;
              do
              {
                *(_BYTE *)v19 = 0;
                v19 = (unsigned __int16 **)((char *)v19 + 1);
                --v18;
              }
              while ( v18 );
              while ( 1 )
              {
                v20 = SysAllocString((&v45)[v14]);
                v13[v14] = v20;
                if ( !v20 )
                  break;
                if ( ++v14 >= 2 )
                  goto LABEL_16;
              }
              for ( j = 0; j < v14; ++j )
                SysFreeString(v13[j]);
            }
          }
          else
          {
            v22 = 8;
            psz = L"DMChannel";
            v23 = (unsigned __int16 **)CoTaskMemAlloc(8u);
            v13 = v23;
            if ( !v23 )
              goto LABEL_20;
            v14 = 0;
            do
            {
              *(_BYTE *)v23 = 0;
              v23 = (unsigned __int16 **)((char *)v23 + 1);
              --v22;
            }
            while ( v22 );
            v24 = 0;
            while ( 1 )
            {
              v25 = SysAllocString((&psz)[v24]);
              v13[v24] = v25;
              if ( !v25 )
                break;
              ++v14;
              if ( ++v24 )
                goto LABEL_16;
            }
            for ( k = 0; k < v14; ++k )
              SysFreeString(v13[k]);
          }
        }
        else
        {
          v27 = 8;
          psz = (OLECHAR *)L"MdmConfiguration";
          v28 = (unsigned __int16 **)CoTaskMemAlloc(8u);
          v13 = v28;
          if ( !v28 )
            goto LABEL_20;
          v14 = 0;
          do
          {
            *(_BYTE *)v28 = 0;
            v28 = (unsigned __int16 **)((char *)v28 + 1);
            --v27;
          }
          while ( v27 );
          v29 = 0;
          while ( 1 )
          {
            v30 = SysAllocString((&psz)[v29]);
            v13[v29] = v30;
            if ( !v30 )
              break;
            ++v14;
            if ( ++v29 )
              goto LABEL_16;
          }
          for ( m = 0; m < v14; ++m )
            SysFreeString(v13[m]);
        }
      }
      else
      {
        v32 = 16;
        v45 = L"Collectors";
        v46 = L"Channels";
        v33 = (unsigned __int16 **)CoTaskMemAlloc(0x10u);
        v13 = v33;
        if ( !v33 )
          goto LABEL_20;
        v14 = 0;
        do
        {
          *(_BYTE *)v33 = 0;
          v33 = (unsigned __int16 **)((char *)v33 + 1);
          --v32;
        }
        while ( v32 );
        while ( 1 )
        {
          v34 = SysAllocString((&v45)[v14]);
          v13[v14] = v34;
          if ( !v34 )
            break;
          if ( ++v14 >= 2 )
            goto LABEL_16;
        }
        for ( n = 0; n < v14; ++n )
          SysFreeString(v13[n]);
      }
    }
    else
    {
      v36 = 40;
      v47[0] = L"EtwLog";
      v47[1] = L"FileDownload";
      v47[2] = L"DeviceStateData";
      v47[3] = L"DiagnosticArchive";
      v47[4] = L"Policy";
      v37 = (unsigned __int16 **)CoTaskMemAlloc(0x28u);
      v13 = v37;
      if ( !v37 )
        goto LABEL_20;
      v14 = 0;
      do
      {
        *(_BYTE *)v37 = 0;
        v37 = (unsigned __int16 **)((char *)v37 + 1);
        --v36;
      }
      while ( v36 );
      while ( 1 )
      {
        v38 = SysAllocString(v47[v14]);
        v13[v14] = v38;
        if ( !v38 )
          break;
        if ( ++v14 >= 5 )
        {
LABEL_16:
          *a3 = v13;
          v10 = 0;
          *a2 = v14;
          goto LABEL_69;
        }
      }
      for ( ii = 0; ii < v14; ++ii )
        SysFreeString(v13[ii]);
    }
    CoTaskMemFree(v13);
LABEL_20:
    v10 = -2147024882;
    goto LABEL_69;
  }
  v10 = -2147024809;
LABEL_69:
  if ( (unsigned int)dword_180048E90 > 5 )
  {
    LODWORD(psz) = v10;
    if ( a2 )
      v40 = *a2;
    else
      v40 = -1;
    v49 = v40;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
      this,
      (__int64)byte_18003E7A9,
      (__int64)a3,
      a4,
      (__int64)&v49,
      (__int64)&psz);
  }
  if ( (int)(v10 + 0x80000000) >= 0 && v10 != -2147024809 )
  {
    v41 = *a3;
    if ( *a3 )
    {
      v42 = *a2;
      for ( jj = 0; jj < v42; ++jj )
        SysFreeString(v41[jj]);
      CoTaskMemFree(v41);
    }
    *a3 = 0;
    *a2 = 0;
  }
  return v10;
}

```

## disassembly

```asm
0x180006f60  mov     [rsp-38h+arg_0], rbx
0x180006f65  push    rbp
0x180006f66  push    rsi
0x180006f67  push    rdi
0x180006f68  push    r12
0x180006f6a  push    r13
0x180006f6c  push    r14
0x180006f6e  push    r15
0x180006f70  mov     rbp, rsp
0x180006f73  sub     rsp, 70h
0x180006f77  xor     r13d, r13d
0x180006f7a  mov     r12, r8
0x180006f7d  mov     r15, rdx
0x180006f80  test    rdx, rdx
0x180006f83  jz      loc_180007308
0x180006f89  test    r8, r8
0x180006f8c  jz      loc_180007308
0x180006f92  mov     [rdx], r13d
0x180006f95  mov     [r8], r13
0x180006f98  mov     ecx, [rcx+2Ch]
0x180006f9b  test    ecx, ecx
0x180006f9d  jz      loc_180007265
0x180006fa3  sub     ecx, 1
0x180006fa6  jz      loc_1800071E3
0x180006fac  sub     ecx, 11h
0x180006faf  jz      loc_180007164
0x180006fb5  sub     ecx, 2
0x180006fb8  jz      loc_1800070E5
0x180006fbe  sub     ecx, 9
0x180006fc1  jz      loc_18000706B
0x180006fc7  cmp     ecx, 3
0x180006fca  jz      short loc_180006FDC
0x180006fcc  mov     [rdx], r13d
0x180006fcf  mov     [r8], r13
0x180006fd2  mov     ebx, 86000011h
0x180006fd7  jmp     loc_18000730D
0x180006fdc  lea     rax, aChannels; "Channels"
0x180006fe3  mov     ebx, 8
0x180006fe8  mov     ecx, ebx; cb
0x180006fea  mov     [rbp+psz], rax
0x180006fee  call    cs:__imp_CoTaskMemAlloc
0x180006ff4  mov     rsi, rax
0x180006ff7  test    rax, rax
0x180006ffa  jz      short loc_180007061
0x180006ffc  mov     edi, r13d
0x180006fff  mov     [rax], r13b
0x180007002  inc     rax
0x180007005  sub     rbx, 1
0x180007009  jnz     short loc_180006FFF
0x18000700b  mov     r14d, r13d
0x18000700e  mov     ebx, r14d
0x180007011  mov     rcx, [rbp+rbx*8+psz]; psz
0x180007016  call    cs:__imp_SysAllocString
0x18000701c  mov     [rsi+rbx*8], rax
0x180007020  test    rax, rax
0x180007023  jz      short loc_18000703F
0x180007025  inc     edi
0x180007027  inc     r14d
0x18000702a  cmp     r14d, 1
0x18000702e  jb      short loc_18000700E
0x180007030  mov     [r12], rsi
0x180007034  mov     ebx, r13d
0x180007037  mov     [r15], edi
0x18000703a  jmp     loc_18000730D
0x18000703f  mov     ebx, r13d
0x180007042  test    edi, edi
0x180007044  jz      short loc_180007058
0x180007046  mov     ecx, ebx
0x180007048  mov     rcx, [rsi+rcx*8]; bstrString
0x18000704c  call    cs:__imp_SysFreeString
0x180007052  inc     ebx
0x180007054  cmp     ebx, edi
0x180007056  jb      short loc_180007046
0x180007058  mov     rcx, rsi; pv
0x18000705b  call    cs:__imp_CoTaskMemFree
0x180007061  mov     ebx, 8007000Eh
0x180007066  jmp     loc_18000730D
0x18000706b  lea     rax, aArchivedefinit; "ArchiveDefinition"
0x180007072  mov     ebx, 10h
0x180007077  mov     [rbp+var_40], rax
0x18000707b  mov     ecx, ebx; cb
0x18000707d  lea     rax, aArchiveresults; "ArchiveResults"
0x180007084  mov     [rbp+var_38], rax
0x180007088  call    cs:__imp_CoTaskMemAlloc
0x18000708e  mov     rsi, rax
0x180007091  test    rax, rax
0x180007094  jz      short loc_180007061
0x180007096  mov     edi, r13d
0x180007099  mov     [rax], r13b
0x18000709c  inc     rax
0x18000709f  sub     rbx, 1
0x1800070a3  jnz     short loc_180007099
0x1800070a5  mov     ebx, edi
0x1800070a7  mov     rcx, [rbp+rbx*8+var_40]; psz
0x1800070ac  call    cs:__imp_SysAllocString
0x1800070b2  mov     [rsi+rbx*8], rax
0x1800070b6  test    rax, rax
0x1800070b9  jz      short loc_1800070C7
0x1800070bb  inc     edi
0x1800070bd  cmp     edi, 2
0x1800070c0  jb      short loc_1800070A5
0x1800070c2  jmp     loc_180007030
0x1800070c7  mov     ebx, r13d
0x1800070ca  test    edi, edi
0x1800070cc  jz      short loc_180007058
0x1800070ce  mov     ecx, ebx
0x1800070d0  mov     rcx, [rsi+rcx*8]; bstrString
0x1800070d4  call    cs:__imp_SysFreeString
0x1800070da  inc     ebx
0x1800070dc  cmp     ebx, edi
0x1800070de  jb      short loc_1800070CE
0x1800070e0  jmp     loc_180007058
0x1800070e5  lea     rax, aDmchannel; "DMChannel"
0x1800070ec  mov     ebx, 8
0x1800070f1  mov     ecx, ebx; cb
0x1800070f3  mov     [rbp+psz], rax
0x1800070f7  call    cs:__imp_CoTaskMemAlloc
0x1800070fd  mov     rsi, rax
0x180007100  test    rax, rax
0x180007103  jz      loc_180007061
0x180007109  mov     edi, r13d
0x18000710c  mov     [rax], r13b
0x18000710f  inc     rax
0x180007112  sub     rbx, 1
0x180007116  jnz     short loc_18000710C
0x180007118  mov     r14d, r13d
0x18000711b  mov     ebx, r14d
0x18000711e  mov     rcx, [rbp+rbx*8+psz]; psz
0x180007123  call    cs:__imp_SysAllocString
0x180007129  mov     [rsi+rbx*8], rax
0x18000712d  test    rax, rax
0x180007130  jz      short loc_180007142
0x180007132  inc     edi
0x180007134  inc     r14d
0x180007137  cmp     r14d, 1
0x18000713b  jb      short loc_18000711B
0x18000713d  jmp     loc_180007030
0x180007142  mov     ebx, r13d
0x180007145  test    edi, edi
0x180007147  jz      loc_180007058
0x18000714d  mov     ecx, ebx
0x18000714f  mov     rcx, [rsi+rcx*8]; bstrString
0x180007153  call    cs:__imp_SysFreeString
0x180007159  inc     ebx
0x18000715b  cmp     ebx, edi
0x18000715d  jb      short loc_18000714D
0x18000715f  jmp     loc_180007058
0x180007164  lea     rax, aMdmconfigurati; "MdmConfiguration"
0x18000716b  mov     ebx, 8
0x180007170  mov     ecx, ebx; cb
0x180007172  mov     [rbp+psz], rax
0x180007176  call    cs:__imp_CoTaskMemAlloc
0x18000717c  mov     rsi, rax
0x18000717f  test    rax, rax
0x180007182  jz      loc_180007061
0x180007188  mov     edi, r13d
0x18000718b  mov     [rax], r13b
0x18000718e  inc     rax
0x180007191  sub     rbx, 1
0x180007195  jnz     short loc_18000718B
0x180007197  mov     r14d, r13d
0x18000719a  mov     ebx, r14d
0x18000719d  mov     rcx, [rbp+rbx*8+psz]; psz
0x1800071a2  call    cs:__imp_SysAllocString
0x1800071a8  mov     [rsi+rbx*8], rax
0x1800071ac  test    rax, rax
0x1800071af  jz      short loc_1800071C1
0x1800071b1  inc     edi
0x1800071b3  inc     r14d
0x1800071b6  cmp     r14d, 1
0x1800071ba  jb      short loc_18000719A
0x1800071bc  jmp     loc_180007030
0x1800071c1  mov     ebx, r13d
0x1800071c4  test    edi, edi
0x1800071c6  jz      loc_180007058
0x1800071cc  mov     ecx, ebx
0x1800071ce  mov     rcx, [rsi+rcx*8]; bstrString
0x1800071d2  call    cs:__imp_SysFreeString
0x1800071d8  inc     ebx
0x1800071da  cmp     ebx, edi
0x1800071dc  jb      short loc_1800071CC
0x1800071de  jmp     loc_180007058
0x1800071e3  lea     rax, aCollectors; "Collectors"
0x1800071ea  mov     ebx, 10h
0x1800071ef  mov     [rbp+var_40], rax
0x1800071f3  mov     ecx, ebx; cb
0x1800071f5  lea     rax, aChannels; "Channels"
0x1800071fc  mov     [rbp+var_38], rax
0x180007200  call    cs:__imp_CoTaskMemAlloc
0x180007206  mov     rsi, rax
0x180007209  test    rax, rax
0x18000720c  jz      loc_180007061
0x180007212  mov     edi, r13d
0x180007215  mov     [rax], r13b
0x180007218  inc     rax
0x18000721b  sub     rbx, 1
0x18000721f  jnz     short loc_180007215
0x180007221  mov     ebx, edi
0x180007223  mov     rcx, [rbp+rbx*8+var_40]; psz
0x180007228  call    cs:__imp_SysAllocString
0x18000722e  mov     [rsi+rbx*8], rax
0x180007232  test    rax, rax
0x180007235  jz      short loc_180007243
0x180007237  inc     edi
0x180007239  cmp     edi, 2
0x18000723c  jb      short loc_180007221
0x18000723e  jmp     loc_180007030
0x180007243  mov     ebx, r13d
0x180007246  test    edi, edi
0x180007248  jz      loc_180007058
0x18000724e  mov     ecx, ebx
0x180007250  mov     rcx, [rsi+rcx*8]; bstrString
0x180007254  call    cs:__imp_SysFreeString
0x18000725a  inc     ebx
0x18000725c  cmp     ebx, edi
0x18000725e  jb      short loc_18000724E
0x180007260  jmp     loc_180007058
0x180007265  lea     rax, aEtwlog; "EtwLog"
0x18000726c  mov     ebx, 28h ; '('
0x180007271  mov     [rbp+var_30], rax
0x180007275  mov     ecx, ebx; cb
0x180007277  lea     rax, aFiledownload; "FileDownload"
0x18000727e  mov     [rbp+var_28], rax
0x180007282  lea     rax, aDevicestatedat; "DeviceStateData"
0x180007289  mov     [rbp+var_20], rax
0x18000728d  lea     rax, aDiagnosticarch; "DiagnosticArchive"
0x180007294  mov     [rbp+var_18], rax
0x180007298  lea     rax, aPolicy; "Policy"
0x18000729f  mov     [rbp+var_10], rax
0x1800072a3  call    cs:__imp_CoTaskMemAlloc
0x1800072a9  mov     rsi, rax
0x1800072ac  test    rax, rax
0x1800072af  jz      loc_180007061
0x1800072b5  mov     edi, r13d
0x1800072b8  mov     [rax], r13b
0x1800072bb  inc     rax
0x1800072be  sub     rbx, 1
0x1800072c2  jnz     short loc_1800072B8
0x1800072c4  mov     ebx, edi
0x1800072c6  mov     rcx, [rbp+rbx*8+var_30]; psz
0x1800072cb  call    cs:__imp_SysAllocString
0x1800072d1  mov     [rsi+rbx*8], rax
0x1800072d5  test    rax, rax
0x1800072d8  jz      short loc_1800072E6
0x1800072da  inc     edi
0x1800072dc  cmp     edi, 5
0x1800072df  jb      short loc_1800072C4
0x1800072e1  jmp     loc_180007030
0x1800072e6  mov     ebx, r13d
0x1800072e9  test    edi, edi
0x1800072eb  jz      loc_180007058
0x1800072f1  mov     ecx, ebx
0x1800072f3  mov     rcx, [rsi+rcx*8]; bstrString
0x1800072f7  call    cs:__imp_SysFreeString
0x1800072fd  inc     ebx
0x1800072ff  cmp     ebx, edi
0x180007301  jb      short loc_1800072F1
0x180007303  jmp     loc_180007058
0x180007308  mov     ebx, 80070057h
0x18000730d  mov     eax, cs:dword_180048E90
0x180007313  cmp     eax, 5
0x180007316  jbe     short loc_180007349
0x180007318  mov     dword ptr [rbp+psz], ebx
0x18000731b  test    r15, r15
0x18000731e  jz      short loc_180007325
0x180007320  mov     eax, [r15]
0x180007323  jmp     short loc_180007328
0x180007325  or      eax, 0FFFFFFFFh
0x180007328  mov     [rbp+arg_18], eax
0x18000732b  lea     rdx, byte_18003E7A9
0x180007332  lea     rax, [rbp+psz]
0x180007336  mov     [rsp+70h+var_48], rax
0x18000733b  lea     rax, [rbp+arg_18]
0x18000733f  mov     [rsp+70h+var_50], rax
0x180007344  call    ??$Write@U?$_tlgWrapperByVal@$03@@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@3@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x180007349  mov     ecx, 80000000h
0x18000734e  lea     eax, [rbx+rcx]
0x180007351  test    ecx, eax
0x180007353  jnz     short loc_180007394
0x180007355  cmp     ebx, 80070057h
0x18000735b  jz      short loc_180007394
0x18000735d  mov     rdi, [r12]
0x180007361  test    rdi, rdi
0x180007364  jz      short loc_18000738D
0x180007366  mov     r14d, [r15]
0x180007369  mov     esi, r13d
0x18000736c  test    r14d, r14d
0x18000736f  jz      short loc_180007384
0x180007371  mov     ecx, esi
0x180007373  mov     rcx, [rdi+rcx*8]; bstrString
0x180007377  call    cs:__imp_SysFreeString
0x18000737d  inc     esi
0x18000737f  cmp     esi, r14d
0x180007382  jb      short loc_180007371
0x180007384  mov     rcx, rdi; pv
0x180007387  call    cs:__imp_CoTaskMemFree
0x18000738d  mov     [r12], r13
0x180007391  mov     [r15], r13d
0x180007394  mov     eax, ebx
0x180007396  mov     rbx, [rsp+70h+arg_0]
  ... truncated ...
```
