# SchedXmlFile

- ea: `0x10007ff5`
- end: `0x100083f0`
- name: `SchedXmlFile`
- size: `1019`
- prototype: `int __stdcall(MSIHANDLE hInstall)`
- caller_count: `0`
- callee_count: `15`
- tags: `file_ops, registry_config, installer_update`

## callees

- `0x100070ac`
- `0x1000722e`
- `0x1000754f`
- `0x10007ff5`
- `0x1000a63e`
- `0x1000a952`
- `0x1000d4ae`
- `0x1000d51f`
- `0x1000d9ab`
- `0x1000da66`
- `0x1000e070`
- `0x1000e13e`
- `0x1000ec26`
- `0x1000ece0`
- `0x1000f1d7`

## import_xrefs

- `KERNEL32!lstrcmpW` at `0x100080aa`
- `KERNEL32!lstrcmpW` at `0x10008103`
- `KERNEL32!lstrcmpW` at `0x100080aa`
- `KERNEL32!lstrcmpW` at `0x10008103`

## string_xrefs

- `0x1000837e`: `failed to write file indicator to custom action data`
- `0x10007fff`: `SchedXmlFile`
- `0x1000804d`: `Skipping SchedXmlFile because XmlFile table not present`
- `0x10008065`: `failed to read XmlFile table`
- `0x10008193`: `failed to write delete element action indicator to custom action data`
- `0x100082b8`: `failed to write delete value action indicator to custom action data`
- `0x100081cb`: `failed to write Preserve Date indicator to custom action data`
- `0x1000835d`: `failed to write Don't Preserve Date indicator to custom action data`
- `0x10008356`: `failed to write uninstall change data`
- `0x10008385`: `failed to copy file name`
- `0x10008299`: `failed to write create element action indicator to custom action data`
- `0x100082d7`: `failed to write builkwrite value action indicator to custom action data`
- `0x10008377`: `failed to write change data`
- `0x100083a3`: `ExecXmlFile`
- `0x100083b3`: `failed to schedule ExecXmlFile action`

## pseudocode

```c
int __stdcall SchedXmlFile(MSIHANDLE hInstall)
{
  int v1; // edi
  int v2; // eax
  int v3; // esi
  int v4; // eax
  LPCWSTR i; // ebx
  const WCHAR *v6; // ecx
  LPCWSTR v7; // esi
  int v8; // eax
  int v9; // eax
  int v10; // eax
  MSIHANDLE hRecord; // [esp+8h] [ebp-1Ch] BYREF
  LPCWSTR v13; // [esp+Ch] [ebp-18h] BYREF
  int v14; // [esp+10h] [ebp-14h]
  int v15; // [esp+14h] [ebp-10h]
  int v16; // [esp+18h] [ebp-Ch]
  LPCWSTR lpString1; // [esp+1Ch] [ebp-8h] BYREF
  LPCWSTR szValue; // [esp+20h] [ebp-4h] BYREF
  MSIHANDLE hInstalla; // [esp+2Ch] [ebp+8h]

  v1 = 0;
  lpString1 = 0;
  v16 = 0;
  v14 = 0;
  v13 = 0;
  hRecord = 0;
  szValue = 0;
  v15 = 0;
  v2 = sub_1000D51F(hInstall, (int)"SchedXmlFile");
  v3 = v2;
  if ( v2 < 0 )
  {
    sub_1000DA66(v2, "failed to initialize");
    goto LABEL_71;
  }
  v4 = sub_1000722E((int)&v13, (MSIHANDLE)&hRecord);
  v3 = v4;
  if ( v4 == 1 )
  {
    sub_1000D9AB(1, "Skipping SchedXmlFile because XmlFile table not present");
    v3 = 0;
    goto LABEL_71;
  }
  if ( v4 < 0 )
  {
    sub_1000DA66(v4, "%s");
    sub_1000E13E(25530, v3, INSTALLMESSAGE_ERROR, 0);
    goto LABEL_71;
  }
  for ( i = v13; i; i = (LPCWSTR)*((_DWORD *)i + 302) )
  {
    if ( lpString1 )
    {
      if ( !lstrcmpW(lpString1, i + 78) && *((_DWORD *)i + 302) && v14 == (*((_DWORD *)i + 299) & 0x100) )
        goto LABEL_38;
      v6 = lpString1;
      if ( lpString1 )
      {
        if ( *((_DWORD *)i + 302) )
        {
          v7 = (LPCWSTR)*((_DWORD *)i + 301);
          hInstalla = (MSIHANDLE)v7;
        }
        else
        {
          v7 = i;
          hInstalla = (MSIHANDLE)i;
        }
        if ( v7 )
        {
          while ( !lstrcmpW(v6, v7 + 78) && v14 == (*((_DWORD *)v7 + 299) & 0x100) )
          {
            if ( sub_1000ECE0(*((_DWORD *)v7 + 37), *((_DWORD *)v7 + 38)) )
            {
              v8 = *((_DWORD *)v7 + 299);
              if ( (v8 & 0x10000) == 0 )
              {
                if ( !v16 )
                {
                  v3 = sub_100070AC(lpString1, v7, (int)&szValue);
                  if ( v3 < 0 )
                    goto LABEL_63;
                  ++v15;
                  v16 = 1;
                  v8 = *(_DWORD *)(hInstalla + 1196);
                }
                if ( (v8 & 1) != 0 )
                {
                  v3 = sub_1000F1D7(6, &szValue);
                  if ( v3 < 0 )
                  {
                    sub_1000DA66(v3, "failed to write delete element action indicator to custom action data");
                    goto LABEL_71;
                  }
                }
                else
                {
                  v3 = sub_1000F1D7(4, &szValue);
                  if ( v3 < 0 )
                    goto LABEL_47;
                }
                if ( (*((_DWORD *)i + 299) & 0x1000) != 0 )
                {
                  v3 = sub_1000F1D7(1, &szValue);
                  if ( v3 < 0 )
                    goto LABEL_30;
                }
                else
                {
                  v3 = sub_1000F1D7(0, &szValue);
                  if ( v3 < 0 )
                    goto LABEL_62;
                }
                v3 = sub_1000754F(hInstalla, &szValue);
                if ( v3 < 0 )
                {
                  sub_1000DA66(v3, "failed to write uninstall change data");
                  goto LABEL_71;
                }
                v7 = (LPCWSTR)hInstalla;
              }
            }
            v7 = (LPCWSTR)*((_DWORD *)v7 + 301);
            hInstalla = (MSIHANDLE)v7;
            if ( !v7 )
              break;
            v6 = lpString1;
          }
        }
      }
    }
    v3 = sub_1000A63E((int)&lpString1, i + 78, 0);
    if ( v3 < 0 )
    {
      sub_1000DA66(v3, "failed to copy file name");
      goto LABEL_71;
    }
    v9 = *((_DWORD *)i + 299) & 0x100;
    v16 = 0;
    v14 = v9;
LABEL_38:
    if ( sub_1000EC26(*((_DWORD *)i + 37), *((_DWORD *)i + 38)) )
    {
      if ( !v16 )
      {
        v3 = sub_100070AC(lpString1, i, (int)&szValue);
        if ( v3 < 0 )
        {
LABEL_63:
          sub_1000DA66(v3, "failed to begin file change for file: %ls");
          goto LABEL_71;
        }
        ++v15;
        v16 = 1;
      }
      v10 = *((_DWORD *)i + 299);
      if ( (v10 & 1) != 0 )
      {
        v3 = sub_1000F1D7(5, &szValue);
        if ( v3 < 0 )
        {
          sub_1000DA66(v3, "failed to write create element action indicator to custom action data");
          goto LABEL_71;
        }
      }
      else if ( (v10 & 2) != 0 )
      {
        v3 = sub_1000F1D7(4, &szValue);
        if ( v3 < 0 )
        {
LABEL_47:
          sub_1000DA66(v3, "failed to write delete value action indicator to custom action data");
          goto LABEL_71;
        }
      }
      else if ( (v10 & 4) != 0 )
      {
        v3 = sub_1000F1D7(7, &szValue);
        if ( v3 < 0 )
        {
          sub_1000DA66(v3, "failed to write builkwrite value action indicator to custom action data");
          goto LABEL_71;
        }
      }
      else
      {
        v3 = sub_1000F1D7(3, &szValue);
        if ( v3 < 0 )
        {
          sub_1000DA66(v3, "failed to write file indicator to custom action data");
          goto LABEL_71;
        }
      }
      if ( (*((_DWORD *)i + 299) & 0x1000) != 0 )
      {
        v3 = sub_1000F1D7(1, &szValue);
        if ( v3 < 0 )
        {
LABEL_30:
          sub_1000DA66(v3, "failed to write Preserve Date indicator to custom action data");
          goto LABEL_71;
        }
      }
      else
      {
        v3 = sub_1000F1D7(0, &szValue);
        if ( v3 < 0 )
        {
LABEL_62:
          sub_1000DA66(v3, "failed to write Don't Preserve Date indicator to custom action data");
          goto LABEL_71;
        }
      }
      v3 = sub_1000754F(i, &szValue);
      if ( v3 < 0 )
      {
        sub_1000DA66(v3, "failed to write change data");
        goto LABEL_71;
      }
    }
  }
  v3 = v3 != -2147024637 ? v3 : 0;
  if ( v3 >= 0 )
  {
    if ( szValue )
    {
      if ( *szValue )
      {
        v3 = sub_1000E070(L"ExecXmlFile", szValue, 1000 * v15);
        if ( v3 < 0 )
          sub_1000DA66(v3, "failed to schedule ExecXmlFile action");
      }
    }
  }
  else
  {
    sub_1000DA66(v3, "failed while looping through all objects to secure");
  }
LABEL_71:
  if ( lpString1 )
    sub_1000A952(lpString1);
  if ( szValue )
    sub_1000A952(szValue);
  if ( v3 < 0 )
    v1 = 1603;
  return sub_1000D4AE(v1);
}

```

## disassembly

```asm
0x10007ff5  push    ebp
0x10007ff6  mov     ebp, esp
0x10007ff8  sub     esp, 1Ch
0x10007ffb  push    esi
0x10007ffc  push    edi
0x10007ffd  xor     edi, edi
0x10007fff  push    offset aSchedxmlfile_0; "SchedXmlFile"
0x10008004  push    [ebp+hInstall]; hInstall
0x10008007  mov     [ebp+lpString1], edi
0x1000800a  mov     [ebp+var_C], edi
0x1000800d  mov     [ebp+var_14], edi
0x10008010  mov     [ebp+var_18], edi
0x10008013  mov     [ebp+hRecord], edi
0x10008016  mov     [ebp+szValue], edi
0x10008019  mov     [ebp+var_10], edi
0x1000801c  call    sub_1000D51F
0x10008021  mov     esi, eax
0x10008023  test    esi, esi
0x10008025  jns     short loc_10008039
0x10008027  push    offset aFailedToInitia_2; "failed to initialize"
0x1000802c  push    esi
0x1000802d  call    sub_1000DA66
0x10008032  pop     ecx
0x10008033  pop     ecx
0x10008034  jmp     loc_100083C1
0x10008039  lea     eax, [ebp+hRecord]
0x1000803c  push    eax; hRecord
0x1000803d  lea     eax, [ebp+var_18]
0x10008040  push    eax; int
0x10008041  call    sub_1000722E
0x10008046  mov     esi, eax
0x10008048  cmp     esi, 1
0x1000804b  jnz     short loc_10008061
0x1000804d  push    offset aSkippingSchedx; "Skipping SchedXmlFile because XmlFile t"...
0x10008052  push    eax
0x10008053  call    sub_1000D9AB
0x10008058  pop     ecx
0x10008059  pop     ecx
0x1000805a  mov     esi, edi
0x1000805c  jmp     loc_100083C1
0x10008061  test    esi, esi
0x10008063  jns     short loc_1000808E
0x10008065  push    offset aFailedToReadXm; "failed to read XmlFile table"
0x1000806a  push    offset aS_1; "%s"
0x1000806f  push    esi
0x10008070  call    sub_1000DA66
0x10008075  push    edi; int
0x10008076  push    1000000h; eMessageType
0x1000807b  push    esi; int
0x1000807c  push    63BAh; iValue
0x10008081  call    sub_1000E13E
0x10008086  add     esp, 1Ch
0x10008089  jmp     loc_100083C1
0x1000808e  push    ebx
0x1000808f  mov     ebx, [ebp+var_18]
0x10008092  jmp     loc_10008337
0x10008097  cmp     [ebp+lpString1], edi
0x1000809a  jz      loc_10008213
0x100080a0  lea     eax, [ebx+9Ch]
0x100080a6  push    eax; lpString2
0x100080a7  push    [ebp+lpString1]; lpString1
0x100080aa  call    ds:lstrcmpW
0x100080b0  test    eax, eax
0x100080b2  jnz     short loc_100080D0
0x100080b4  cmp     [ebx+4B8h], edi
0x100080ba  jz      short loc_100080D0
0x100080bc  mov     eax, [ebx+4ACh]
0x100080c2  and     eax, 100h
0x100080c7  cmp     [ebp+var_14], eax
0x100080ca  jz      loc_1000823F
0x100080d0  mov     ecx, [ebp+lpString1]
0x100080d3  test    ecx, ecx
0x100080d5  jz      loc_10008213
0x100080db  cmp     [ebx+4B8h], edi
0x100080e1  jz      short loc_100080EE
0x100080e3  mov     esi, [ebx+4B4h]
0x100080e9  mov     [ebp+hInstall], esi
0x100080ec  jmp     short loc_100080F3
0x100080ee  mov     esi, ebx
0x100080f0  mov     [ebp+hInstall], ebx
0x100080f3  test    esi, esi
0x100080f5  jz      loc_10008213
0x100080fb  lea     eax, [esi+9Ch]
0x10008101  push    eax; lpString2
0x10008102  push    ecx; lpString1
0x10008103  call    ds:lstrcmpW
0x10008109  test    eax, eax
0x1000810b  jnz     loc_10008213
0x10008111  mov     eax, [esi+4ACh]
0x10008117  and     eax, 100h
0x1000811c  cmp     [ebp+var_14], eax
0x1000811f  jnz     loc_10008213
0x10008125  push    dword ptr [esi+98h]
0x1000812b  push    dword ptr [esi+94h]
0x10008131  call    sub_1000ECE0
0x10008136  test    eax, eax
0x10008138  jz      loc_100081FE
0x1000813e  mov     eax, [esi+4ACh]
0x10008144  test    eax, 10000h
0x10008149  jnz     loc_100081FE
0x1000814f  cmp     [ebp+var_C], edi
0x10008152  jnz     short loc_1000817E
0x10008154  lea     eax, [ebp+szValue]
0x10008157  push    eax; int
0x10008158  push    esi; szValue
0x10008159  push    [ebp+lpString1]; lpFileName
0x1000815c  call    sub_100070AC
0x10008161  mov     esi, eax
0x10008163  test    esi, esi
0x10008165  js      loc_10008364
0x1000816b  mov     eax, [ebp+hInstall]
0x1000816e  inc     [ebp+var_10]
0x10008171  mov     [ebp+var_C], 1
0x10008178  mov     eax, [eax+4ACh]
0x1000817e  test    al, 1
0x10008180  lea     eax, [ebp+szValue]
0x10008183  push    eax
0x10008184  jz      short loc_1000819D
0x10008186  push    6
0x10008188  call    sub_1000F1D7
0x1000818d  mov     esi, eax
0x1000818f  test    esi, esi
0x10008191  jns     short loc_100081AE
0x10008193  push    offset aFailedToWriteD_0; "failed to write delete element action i"...
0x10008198  jmp     loc_100083B8
0x1000819d  push    4
0x1000819f  call    sub_1000F1D7
0x100081a4  mov     esi, eax
0x100081a6  test    esi, esi
0x100081a8  js      loc_100082B8
0x100081ae  test    dword ptr [ebx+4ACh], 1000h
0x100081b8  lea     eax, [ebp+szValue]
0x100081bb  push    eax
0x100081bc  jz      short loc_100081D5
0x100081be  push    1
0x100081c0  call    sub_1000F1D7
0x100081c5  mov     esi, eax
0x100081c7  test    esi, esi
0x100081c9  jns     short loc_100081E5
0x100081cb  push    offset aFailedToWriteP; "failed to write Preserve Date indicator"...
0x100081d0  jmp     loc_100083B8
0x100081d5  push    edi
0x100081d6  call    sub_1000F1D7
0x100081db  mov     esi, eax
0x100081dd  test    esi, esi
0x100081df  js      loc_1000835D
0x100081e5  lea     eax, [ebp+szValue]
0x100081e8  push    eax
0x100081e9  push    [ebp+hInstall]
0x100081ec  call    sub_1000754F
0x100081f1  mov     esi, eax
0x100081f3  test    esi, esi
0x100081f5  js      loc_10008356
0x100081fb  mov     esi, [ebp+hInstall]
0x100081fe  mov     esi, [esi+4B4h]
0x10008204  mov     [ebp+hInstall], esi
0x10008207  test    esi, esi
0x10008209  jz      short loc_10008213
0x1000820b  mov     ecx, [ebp+lpString1]
0x1000820e  jmp     loc_100080FB
0x10008213  push    edi; int
0x10008214  lea     eax, [ebx+9Ch]
0x1000821a  push    eax; lpString
0x1000821b  lea     eax, [ebp+lpString1]
0x1000821e  push    eax; int
0x1000821f  call    sub_1000A63E
0x10008224  mov     esi, eax
0x10008226  test    esi, esi
0x10008228  js      loc_10008385
0x1000822e  mov     eax, [ebx+4ACh]
0x10008234  and     eax, 100h
0x10008239  mov     [ebp+var_C], edi
0x1000823c  mov     [ebp+var_14], eax
0x1000823f  push    dword ptr [ebx+98h]
0x10008245  push    dword ptr [ebx+94h]
0x1000824b  call    sub_1000EC26
0x10008250  test    eax, eax
0x10008252  jz      loc_10008331
0x10008258  cmp     [ebp+var_C], edi
0x1000825b  jnz     short loc_1000827E
0x1000825d  lea     eax, [ebp+szValue]
0x10008260  push    eax; int
0x10008261  push    ebx; szValue
0x10008262  push    [ebp+lpString1]; lpFileName
0x10008265  call    sub_100070AC
0x1000826a  mov     esi, eax
0x1000826c  test    esi, esi
0x1000826e  js      loc_10008364
0x10008274  inc     [ebp+var_10]
0x10008277  mov     [ebp+var_C], 1
0x1000827e  mov     eax, [ebx+4ACh]
0x10008284  test    al, 1
0x10008286  jz      short loc_100082A3
0x10008288  lea     eax, [ebp+szValue]
0x1000828b  push    eax
0x1000828c  push    5
0x1000828e  call    sub_1000F1D7
0x10008293  mov     esi, eax
0x10008295  test    esi, esi
0x10008297  jns     short loc_100082F2
0x10008299  push    offset aFailedToWriteC_0; "failed to write create element action i"...
0x1000829e  jmp     loc_100083B8
0x100082a3  test    al, 2
0x100082a5  jz      short loc_100082C2
0x100082a7  lea     eax, [ebp+szValue]
0x100082aa  push    eax
0x100082ab  push    4
0x100082ad  call    sub_1000F1D7
0x100082b2  mov     esi, eax
0x100082b4  test    esi, esi
0x100082b6  jns     short loc_100082F2
0x100082b8  push    offset aFailedToWriteD_1; "failed to write delete value action ind"...
0x100082bd  jmp     loc_100083B8
0x100082c2  test    al, 4
0x100082c4  lea     eax, [ebp+szValue]
0x100082c7  push    eax
0x100082c8  jz      short loc_100082E1
0x100082ca  push    7
0x100082cc  call    sub_1000F1D7
0x100082d1  mov     esi, eax
0x100082d3  test    esi, esi
0x100082d5  jns     short loc_100082F2
0x100082d7  push    offset aFailedToWriteB; "failed to write builkwrite value action"...
0x100082dc  jmp     loc_100083B8
0x100082e1  push    3
0x100082e3  call    sub_1000F1D7
0x100082e8  mov     esi, eax
0x100082ea  test    esi, esi
0x100082ec  js      loc_1000837E
0x100082f2  test    dword ptr [ebx+4ACh], 1000h
0x100082fc  lea     eax, [ebp+szValue]
0x100082ff  push    eax
0x10008300  jz      short loc_10008315
0x10008302  push    1
0x10008304  call    sub_1000F1D7
0x10008309  mov     esi, eax
0x1000830b  test    esi, esi
0x1000830d  js      loc_100081CB
0x10008313  jmp     short loc_10008321
0x10008315  push    edi
0x10008316  call    sub_1000F1D7
0x1000831b  mov     esi, eax
0x1000831d  test    esi, esi
0x1000831f  js      short loc_1000835D
0x10008321  lea     eax, [ebp+szValue]
0x10008324  push    eax
0x10008325  push    ebx
0x10008326  call    sub_1000754F
0x1000832b  mov     esi, eax
0x1000832d  test    esi, esi
0x1000832f  js      short loc_10008377
0x10008331  mov     ebx, [ebx+4B8h]
0x10008337  test    ebx, ebx
0x10008339  jnz     loc_10008097
0x1000833f  lea     eax, [esi+7FF8FEFDh]
0x10008345  neg     eax
0x10008347  sbb     eax, eax
0x10008349  and     esi, eax
0x1000834b  mov     eax, esi
0x1000834d  jge     short loc_1000838C
0x1000834f  push    offset aFailedWhileLoo_2; "failed while looping through all object"...
0x10008354  jmp     short loc_100083B8
0x10008356  push    offset aFailedToWriteU; "failed to write uninstall change data"
0x1000835b  jmp     short loc_100083B8
0x1000835d  push    offset aFailedToWriteD_2; "failed to write Don't Preserve Date ind"...
0x10008362  jmp     short loc_100083B8
0x10008364  push    [ebp+lpString1]
0x10008367  push    offset aFailedToBeginF; "failed to begin file change for file: %"...
0x1000836c  push    esi
0x1000836d  call    sub_1000DA66
0x10008372  add     esp, 0Ch
0x10008375  jmp     short loc_100083C0
0x10008377  push    offset aFailedToWriteC_1; "failed to write change data"
0x1000837c  jmp     short loc_100083B8
0x1000837e  push    offset aFailedToWriteF; "failed to write file indicator to custo"...
0x10008383  jmp     short loc_100083B8
0x10008385  push    offset aFailedToCopyFi; "failed to copy file name"
0x1000838a  jmp     short loc_100083B8
0x1000838c  mov     ecx, [ebp+szValue]
0x1000838f  test    ecx, ecx
0x10008391  jz      short loc_100083C0
0x10008393  mov     esi, eax
0x10008395  cmp     [ecx], di
0x10008398  jz      short loc_100083C0
0x1000839a  imul    eax, [ebp+var_10], 3E8h
0x100083a1  push    eax; iValue
0x100083a2  push    ecx; szValue
0x100083a3  push    offset aExecxmlfile_1; "ExecXmlFile"
0x100083a8  call    sub_1000E070
0x100083ad  mov     esi, eax
0x100083af  test    esi, esi
0x100083b1  jns     short loc_100083C0
0x100083b3  push    offset aFailedToSchedu_6; "failed to schedule ExecXmlFile action"
0x100083b8  push    esi
0x100083b9  call    sub_1000DA66
0x100083be  pop     ecx
0x100083bf  pop     ecx
0x100083c0  pop     ebx
0x100083c1  cmp     [ebp+lpString1], edi
0x100083c4  jz      short loc_100083CE
  ... truncated ...
```
