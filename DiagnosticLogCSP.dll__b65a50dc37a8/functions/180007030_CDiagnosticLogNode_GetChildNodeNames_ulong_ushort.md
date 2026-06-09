# CDiagnosticLogNode::GetChildNodeNames(ulong *,ushort * * *)

- ea: `0x180007030`
- end: `0x180007501`
- name: `?GetChildNodeNames@CDiagnosticLogNode@@UEAAJPEAKPEAPEAPEAG@Z`
- size: `1233`
- prototype: `__int64 __fastcall(CDiagnosticLogNode *__hidden this, unsigned int *, unsigned __int16 ***)`
- caller_count: `0`
- callee_count: `2`
- tags: `registry_config, service_task, broker_com_uri`

## callees

- `0x180001090`
- `0x180007030`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800070be`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180007170`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800071f5`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180007286`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180007322`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800073d7`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800070be`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180007170`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800071f5`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180007286`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180007322`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800073d7`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000713d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800074d3`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000713d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800074d3`
- `OLEAUT32!__imp_SysAllocString` at `0x1800070ec`
- `OLEAUT32!__imp_SysAllocString` at `0x18000719a`
- `OLEAUT32!__imp_SysAllocString` at `0x180007227`
- `OLEAUT32!__imp_SysAllocString` at `0x1800072b8`
- `OLEAUT32!__imp_SysAllocString` at `0x180007350`
- `OLEAUT32!__imp_SysAllocString` at `0x180007405`
- `OLEAUT32!__imp_SysAllocString` at `0x1800070ec`
- `OLEAUT32!__imp_SysAllocString` at `0x18000719a`
- `OLEAUT32!__imp_SysAllocString` at `0x180007227`
- `OLEAUT32!__imp_SysAllocString` at `0x1800072b8`
- `OLEAUT32!__imp_SysAllocString` at `0x180007350`
- `OLEAUT32!__imp_SysAllocString` at `0x180007405`
- `OLEAUT32!__imp_SysFreeString` at `0x180007128`
- `OLEAUT32!__imp_SysFreeString` at `0x1800071cc`
- `OLEAUT32!__imp_SysFreeString` at `0x18000725d`
- `OLEAUT32!__imp_SysFreeString` at `0x1800072ee`
- `OLEAUT32!__imp_SysFreeString` at `0x180007382`
- `OLEAUT32!__imp_SysFreeString` at `0x180007437`
- `OLEAUT32!__imp_SysFreeString` at `0x1800074bd`
- `OLEAUT32!__imp_SysFreeString` at `0x180007128`
- `OLEAUT32!__imp_SysFreeString` at `0x1800071cc`
- `OLEAUT32!__imp_SysFreeString` at `0x18000725d`
- `OLEAUT32!__imp_SysFreeString` at `0x1800072ee`
- `OLEAUT32!__imp_SysFreeString` at `0x180007382`
- `OLEAUT32!__imp_SysFreeString` at `0x180007437`
- `OLEAUT32!__imp_SysFreeString` at `0x1800074bd`

## string_xrefs

- `0x180007274`: `MdmConfiguration`

## pseudocode

```c
__int64 __fastcall CDiagnosticLogNode::GetChildNodeNames(
        CDiagnosticLogNode *this,
        unsigned int *a2,
        unsigned __int16 ***a3,
        int a4)
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
    v6 = *((_DWORD *)this + 11);
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
            LODWORD(this) = v9 - 9;
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
  if ( (unsigned int)dword_18004AE90 > 5 )
  {
    LODWORD(psz) = v10;
    if ( a2 )
      v40 = *a2;
    else
      v40 = -1;
    v49 = v40;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
      (_DWORD)this,
      (unsigned int)byte_1800407A9,
      (_DWORD)a3,
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
0x180007030  mov     [rsp-38h+arg_0], rbx
0x180007035  push    rbp
0x180007036  push    rsi
0x180007037  push    rdi
0x180007038  push    r12
0x18000703a  push    r13
0x18000703c  push    r14
0x18000703e  push    r15
0x180007040  mov     rbp, rsp
0x180007043  sub     rsp, 70h
0x180007047  xor     r13d, r13d
0x18000704a  mov     r12, r8
0x18000704d  mov     r15, rdx
0x180007050  test    rdx, rdx
0x180007053  jz      loc_18000744E
0x180007059  test    r8, r8
0x18000705c  jz      loc_18000744E
0x180007062  mov     [rdx], r13d
0x180007065  mov     [r8], r13
0x180007068  mov     ecx, [rcx+2Ch]
0x18000706b  test    ecx, ecx
0x18000706d  jz      loc_180007399
0x180007073  sub     ecx, 1
0x180007076  jz      loc_180007305
0x18000707c  sub     ecx, 11h
0x18000707f  jz      loc_180007274
0x180007085  sub     ecx, 2
0x180007088  jz      loc_1800071E3
0x18000708e  sub     ecx, 9
0x180007091  jz      loc_180007153
0x180007097  cmp     ecx, 3
0x18000709a  jz      short loc_1800070AC
0x18000709c  mov     [rdx], r13d
0x18000709f  mov     [r8], r13
0x1800070a2  mov     ebx, 86000011h
0x1800070a7  jmp     loc_180007453
0x1800070ac  lea     rax, aChannels; "Channels"
0x1800070b3  mov     ebx, 8
0x1800070b8  mov     ecx, ebx; cb
0x1800070ba  mov     [rbp+psz], rax
0x1800070be  call    cs:__imp_CoTaskMemAlloc
0x1800070c5  nop     dword ptr [rax+rax+00h]
0x1800070ca  mov     rsi, rax
0x1800070cd  test    rax, rax
0x1800070d0  jz      short loc_180007149
0x1800070d2  mov     edi, r13d
0x1800070d5  mov     [rax], r13b
0x1800070d8  inc     rax
0x1800070db  sub     rbx, 1
0x1800070df  jnz     short loc_1800070D5
0x1800070e1  mov     r14d, r13d
0x1800070e4  mov     ebx, r14d
0x1800070e7  mov     rcx, [rbp+rbx*8+psz]; psz
0x1800070ec  call    cs:__imp_SysAllocString
0x1800070f3  nop     dword ptr [rax+rax+00h]
0x1800070f8  mov     [rsi+rbx*8], rax
0x1800070fc  test    rax, rax
0x1800070ff  jz      short loc_18000711B
0x180007101  inc     edi
0x180007103  inc     r14d
0x180007106  cmp     r14d, 1
0x18000710a  jb      short loc_1800070E4
0x18000710c  mov     [r12], rsi
0x180007110  mov     ebx, r13d
0x180007113  mov     [r15], edi
0x180007116  jmp     loc_180007453
0x18000711b  mov     ebx, r13d
0x18000711e  test    edi, edi
0x180007120  jz      short loc_18000713A
0x180007122  mov     ecx, ebx
0x180007124  mov     rcx, [rsi+rcx*8]; bstrString
0x180007128  call    cs:__imp_SysFreeString
0x18000712f  nop     dword ptr [rax+rax+00h]
0x180007134  inc     ebx
0x180007136  cmp     ebx, edi
0x180007138  jb      short loc_180007122
0x18000713a  mov     rcx, rsi; pv
0x18000713d  call    cs:__imp_CoTaskMemFree
0x180007144  nop     dword ptr [rax+rax+00h]
0x180007149  mov     ebx, 8007000Eh
0x18000714e  jmp     loc_180007453
0x180007153  lea     rax, aArchivedefinit; "ArchiveDefinition"
0x18000715a  mov     ebx, 10h
0x18000715f  mov     [rbp+var_40], rax
0x180007163  mov     ecx, ebx; cb
0x180007165  lea     rax, aArchiveresults; "ArchiveResults"
0x18000716c  mov     [rbp+var_38], rax
0x180007170  call    cs:__imp_CoTaskMemAlloc
0x180007177  nop     dword ptr [rax+rax+00h]
0x18000717c  mov     rsi, rax
0x18000717f  test    rax, rax
0x180007182  jz      short loc_180007149
0x180007184  mov     edi, r13d
0x180007187  mov     [rax], r13b
0x18000718a  inc     rax
0x18000718d  sub     rbx, 1
0x180007191  jnz     short loc_180007187
0x180007193  mov     ebx, edi
0x180007195  mov     rcx, [rbp+rbx*8+var_40]; psz
0x18000719a  call    cs:__imp_SysAllocString
0x1800071a1  nop     dword ptr [rax+rax+00h]
0x1800071a6  mov     [rsi+rbx*8], rax
0x1800071aa  test    rax, rax
0x1800071ad  jz      short loc_1800071BB
0x1800071af  inc     edi
0x1800071b1  cmp     edi, 2
0x1800071b4  jb      short loc_180007193
0x1800071b6  jmp     loc_18000710C
0x1800071bb  mov     ebx, r13d
0x1800071be  test    edi, edi
0x1800071c0  jz      loc_18000713A
0x1800071c6  mov     ecx, ebx
0x1800071c8  mov     rcx, [rsi+rcx*8]; bstrString
0x1800071cc  call    cs:__imp_SysFreeString
0x1800071d3  nop     dword ptr [rax+rax+00h]
0x1800071d8  inc     ebx
0x1800071da  cmp     ebx, edi
0x1800071dc  jb      short loc_1800071C6
0x1800071de  jmp     loc_18000713A
0x1800071e3  lea     rax, aDmchannel; "DMChannel"
0x1800071ea  mov     ebx, 8
0x1800071ef  mov     ecx, ebx; cb
0x1800071f1  mov     [rbp+psz], rax
0x1800071f5  call    cs:__imp_CoTaskMemAlloc
0x1800071fc  nop     dword ptr [rax+rax+00h]
0x180007201  mov     rsi, rax
0x180007204  test    rax, rax
0x180007207  jz      loc_180007149
0x18000720d  mov     edi, r13d
0x180007210  mov     [rax], r13b
0x180007213  inc     rax
0x180007216  sub     rbx, 1
0x18000721a  jnz     short loc_180007210
0x18000721c  mov     r14d, r13d
0x18000721f  mov     ebx, r14d
0x180007222  mov     rcx, [rbp+rbx*8+psz]; psz
0x180007227  call    cs:__imp_SysAllocString
0x18000722e  nop     dword ptr [rax+rax+00h]
0x180007233  mov     [rsi+rbx*8], rax
0x180007237  test    rax, rax
0x18000723a  jz      short loc_18000724C
0x18000723c  inc     edi
0x18000723e  inc     r14d
0x180007241  cmp     r14d, 1
0x180007245  jb      short loc_18000721F
0x180007247  jmp     loc_18000710C
0x18000724c  mov     ebx, r13d
0x18000724f  test    edi, edi
0x180007251  jz      loc_18000713A
0x180007257  mov     ecx, ebx
0x180007259  mov     rcx, [rsi+rcx*8]; bstrString
0x18000725d  call    cs:__imp_SysFreeString
0x180007264  nop     dword ptr [rax+rax+00h]
0x180007269  inc     ebx
0x18000726b  cmp     ebx, edi
0x18000726d  jb      short loc_180007257
0x18000726f  jmp     loc_18000713A
0x180007274  lea     rax, aMdmconfigurati; "MdmConfiguration"
0x18000727b  mov     ebx, 8
0x180007280  mov     ecx, ebx; cb
0x180007282  mov     [rbp+psz], rax
0x180007286  call    cs:__imp_CoTaskMemAlloc
0x18000728d  nop     dword ptr [rax+rax+00h]
0x180007292  mov     rsi, rax
0x180007295  test    rax, rax
0x180007298  jz      loc_180007149
0x18000729e  mov     edi, r13d
0x1800072a1  mov     [rax], r13b
0x1800072a4  inc     rax
0x1800072a7  sub     rbx, 1
0x1800072ab  jnz     short loc_1800072A1
0x1800072ad  mov     r14d, r13d
0x1800072b0  mov     ebx, r14d
0x1800072b3  mov     rcx, [rbp+rbx*8+psz]; psz
0x1800072b8  call    cs:__imp_SysAllocString
0x1800072bf  nop     dword ptr [rax+rax+00h]
0x1800072c4  mov     [rsi+rbx*8], rax
0x1800072c8  test    rax, rax
0x1800072cb  jz      short loc_1800072DD
0x1800072cd  inc     edi
0x1800072cf  inc     r14d
0x1800072d2  cmp     r14d, 1
0x1800072d6  jb      short loc_1800072B0
0x1800072d8  jmp     loc_18000710C
0x1800072dd  mov     ebx, r13d
0x1800072e0  test    edi, edi
0x1800072e2  jz      loc_18000713A
0x1800072e8  mov     ecx, ebx
0x1800072ea  mov     rcx, [rsi+rcx*8]; bstrString
0x1800072ee  call    cs:__imp_SysFreeString
0x1800072f5  nop     dword ptr [rax+rax+00h]
0x1800072fa  inc     ebx
0x1800072fc  cmp     ebx, edi
0x1800072fe  jb      short loc_1800072E8
0x180007300  jmp     loc_18000713A
0x180007305  lea     rax, aCollectors; "Collectors"
0x18000730c  mov     ebx, 10h
0x180007311  mov     [rbp+var_40], rax
0x180007315  mov     ecx, ebx; cb
0x180007317  lea     rax, aChannels; "Channels"
0x18000731e  mov     [rbp+var_38], rax
0x180007322  call    cs:__imp_CoTaskMemAlloc
0x180007329  nop     dword ptr [rax+rax+00h]
0x18000732e  mov     rsi, rax
0x180007331  test    rax, rax
0x180007334  jz      loc_180007149
0x18000733a  mov     edi, r13d
0x18000733d  mov     [rax], r13b
0x180007340  inc     rax
0x180007343  sub     rbx, 1
0x180007347  jnz     short loc_18000733D
0x180007349  mov     ebx, edi
0x18000734b  mov     rcx, [rbp+rbx*8+var_40]; psz
0x180007350  call    cs:__imp_SysAllocString
0x180007357  nop     dword ptr [rax+rax+00h]
0x18000735c  mov     [rsi+rbx*8], rax
0x180007360  test    rax, rax
0x180007363  jz      short loc_180007371
0x180007365  inc     edi
0x180007367  cmp     edi, 2
0x18000736a  jb      short loc_180007349
0x18000736c  jmp     loc_18000710C
0x180007371  mov     ebx, r13d
0x180007374  test    edi, edi
0x180007376  jz      loc_18000713A
0x18000737c  mov     ecx, ebx
0x18000737e  mov     rcx, [rsi+rcx*8]; bstrString
0x180007382  call    cs:__imp_SysFreeString
0x180007389  nop     dword ptr [rax+rax+00h]
0x18000738e  inc     ebx
0x180007390  cmp     ebx, edi
0x180007392  jb      short loc_18000737C
0x180007394  jmp     loc_18000713A
0x180007399  lea     rax, aEtwlog; "EtwLog"
0x1800073a0  mov     ebx, 28h ; '('
0x1800073a5  mov     [rbp+var_30], rax
0x1800073a9  mov     ecx, ebx; cb
0x1800073ab  lea     rax, aFiledownload; "FileDownload"
0x1800073b2  mov     [rbp+var_28], rax
0x1800073b6  lea     rax, aDevicestatedat; "DeviceStateData"
0x1800073bd  mov     [rbp+var_20], rax
0x1800073c1  lea     rax, aDiagnosticarch; "DiagnosticArchive"
0x1800073c8  mov     [rbp+var_18], rax
0x1800073cc  lea     rax, aPolicy; "Policy"
0x1800073d3  mov     [rbp+var_10], rax
0x1800073d7  call    cs:__imp_CoTaskMemAlloc
0x1800073de  nop     dword ptr [rax+rax+00h]
0x1800073e3  mov     rsi, rax
0x1800073e6  test    rax, rax
0x1800073e9  jz      loc_180007149
0x1800073ef  mov     edi, r13d
0x1800073f2  mov     [rax], r13b
0x1800073f5  inc     rax
0x1800073f8  sub     rbx, 1
0x1800073fc  jnz     short loc_1800073F2
0x1800073fe  mov     ebx, edi
0x180007400  mov     rcx, [rbp+rbx*8+var_30]; psz
0x180007405  call    cs:__imp_SysAllocString
0x18000740c  nop     dword ptr [rax+rax+00h]
0x180007411  mov     [rsi+rbx*8], rax
0x180007415  test    rax, rax
0x180007418  jz      short loc_180007426
0x18000741a  inc     edi
0x18000741c  cmp     edi, 5
0x18000741f  jb      short loc_1800073FE
0x180007421  jmp     loc_18000710C
0x180007426  mov     ebx, r13d
0x180007429  test    edi, edi
0x18000742b  jz      loc_18000713A
0x180007431  mov     ecx, ebx
0x180007433  mov     rcx, [rsi+rcx*8]; bstrString
0x180007437  call    cs:__imp_SysFreeString
0x18000743e  nop     dword ptr [rax+rax+00h]
0x180007443  inc     ebx
0x180007445  cmp     ebx, edi
0x180007447  jb      short loc_180007431
0x180007449  jmp     loc_18000713A
0x18000744e  mov     ebx, 80070057h
0x180007453  mov     eax, cs:dword_18004AE90
0x180007459  cmp     eax, 5
0x18000745c  jbe     short loc_18000748F
0x18000745e  mov     dword ptr [rbp+psz], ebx
0x180007461  test    r15, r15
0x180007464  jz      short loc_18000746B
0x180007466  mov     eax, [r15]
0x180007469  jmp     short loc_18000746E
0x18000746b  or      eax, 0FFFFFFFFh
0x18000746e  mov     [rbp+arg_18], eax
0x180007471  lea     rdx, byte_1800407A9
0x180007478  lea     rax, [rbp+psz]
0x18000747c  mov     [rsp+70h+var_48], rax
0x180007481  lea     rax, [rbp+arg_18]
0x180007485  mov     [rsp+70h+var_50], rax
0x18000748a  call    ??$Write@U?$_tlgWrapperByVal@$03@@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@3@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x18000748f  mov     ecx, 80000000h
0x180007494  lea     eax, [rbx+rcx]
0x180007497  test    ecx, eax
0x180007499  jnz     short loc_1800074E6
0x18000749b  cmp     ebx, 80070057h
0x1800074a1  jz      short loc_1800074E6
  ... truncated ...
```
