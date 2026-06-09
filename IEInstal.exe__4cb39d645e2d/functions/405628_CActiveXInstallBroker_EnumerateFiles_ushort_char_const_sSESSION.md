# CActiveXInstallBroker::EnumerateFiles(ushort *,char const *,sSESSION *)

- ea: `0x405628`
- end: `0x405766`
- name: `?EnumerateFiles@CActiveXInstallBroker@@QAGJPAGPBDPAUsSESSION@@@Z`
- size: `318`
- prototype: `int __userpurge@<eax>(_WORD *@<edx>, int@<ecx>, CActiveXInstallBroker *this, unsigned __int16 *, const char *, struct sSESSION *)`
- caller_count: `1`
- callee_count: `9`
- tags: `file_ops, service_task, installer_update, broker_com_uri`

## callers

- `0x406040`

## callees

- `0x402eb9`
- `0x402ed3`
- `0x40304d`
- `0x405628`
- `0x406b37`
- `0x406e8a`
- `0x407561`
- `0x407ca8`
- `0x408a2f`

## import_xrefs

- `ole32!CoTaskMemFree` at `0x40570f`
- `ole32!CoTaskMemFree` at `0x40570f`
- `urlmon!Extract` at `0x405719`
- `urlmon!Extract` at `0x405719`

## pseudocode

```c
int __userpurge CActiveXInstallBroker::EnumerateFiles@<eax>(
        _WORD *a1@<edx>,
        int a2@<ecx>,
        CActiveXInstallBroker *this,
        unsigned __int16 *a4,
        const char *a5,
        struct sSESSION *a6)
{
  int v8; // ecx
  signed int IsAuthorized; // esi
  _WORD *v10; // eax
  bool v11; // cf
  int v12; // eax
  const char *v14; // [esp+0h] [ebp-10h]
  struct sFNAME *v15; // [esp+0h] [ebp-10h]
  struct sFNAME *v16; // [esp+0h] [ebp-10h]
  unsigned __int16 **v17; // [esp+4h] [ebp-Ch]
  struct sFNAME **v18; // [esp+4h] [ebp-Ch]
  int v19; // [esp+4h] [ebp-Ch]
  LPVOID pv; // [esp+Ch] [ebp-4h] BYREF

  if ( !CLock::Lock((CLock *)a2) )
  {
    IsAuthorized = -2147024882;
    goto LABEL_28;
  }
  if ( *(int *)(a2 + 28) < 2 )
  {
    IsAuthorized = -2147019873;
    goto LABEL_28;
  }
  if ( !a1 || !this || !a4 || *((_DWORD *)a4 + 202) )
  {
    IsAuthorized = -2147024809;
    goto LABEL_28;
  }
  v10 = *(_WORD **)(a2 + 36);
  while ( 1 )
  {
    LOWORD(v8) = *a1;
    v11 = *a1 < *v10;
    if ( *a1 != *v10 )
      break;
    if ( !(_WORD)v8 )
      goto LABEL_14;
    LOWORD(v8) = a1[1];
    v11 = (unsigned __int16)v8 < v10[1];
    if ( (_WORD)v8 != v10[1] )
      break;
    a1 += 2;
    v10 += 2;
    if ( !(_WORD)v8 )
    {
LABEL_14:
      v12 = 0;
      goto LABEL_16;
    }
  }
  v12 = v11 ? -1 : 1;
LABEL_16:
  if ( v12 )
  {
LABEL_17:
    IsAuthorized = -2147024891;
    goto LABEL_28;
  }
  IsAuthorized = CActiveXInstallBroker::FileIsAuthorized((CActiveXInstallBroker *)a2, (const char *)this, v8);
  if ( IsAuthorized >= 0 )
  {
    IsAuthorized = CreateTempDir((_BYTE *)a4 + 28);
    if ( IsAuthorized >= 0 )
    {
      pv = 0;
      IsAuthorized = SZtoWSZ((unsigned int)&pv, v14, v17);
      if ( IsAuthorized >= 0 )
      {
        if ( !*(_DWORD *)(a2 + 84) && !ContainingPathIsTamperProof((unsigned __int16 *)pv) )
          goto LABEL_17;
        CoTaskMemFree(pv);
        IsAuthorized = Extract(a4, this);
        if ( IsAuthorized >= 0 )
        {
          IsAuthorized = AddFilesToFileList((const char *)(a2 + 76), v15, v18);
          if ( IsAuthorized >= 0 )
          {
            IsAuthorized = SetFileListIntegrityLevel(v16, v19);
            if ( IsAuthorized >= 0 )
              *(_DWORD *)(a2 + 28) = 3;
          }
        }
      }
    }
  }
LABEL_28:
  CLock::Unlock((CLock *)a2);
  return IsAuthorized;
}

```

## disassembly

```asm
0x405628  mov     edi, edi
0x40562a  push    ebp
0x40562b  mov     ebp, esp
0x40562d  push    ecx
0x40562e  push    ebx
0x40562f  push    esi; int
0x405630  push    edi; struct sFNAME *
0x405631  mov     esi, edx
0x405633  mov     edi, ecx
0x405635  call    ?Lock@CLock@@QAEHXZ; CLock::Lock(void)
0x40563a  test    eax, eax
0x40563c  jnz     short loc_405648
0x40563e  mov     esi, 8007000Eh
0x405643  jmp     loc_405756
0x405648  cmp     dword ptr [edi+1Ch], 2
0x40564c  jge     short loc_405658
0x40564e  mov     esi, 8007139Fh
0x405653  jmp     loc_405756
0x405658  test    esi, esi
0x40565a  jz      loc_405751
0x405660  cmp     [ebp+this], 0
0x405664  jz      loc_405751
0x40566a  mov     ebx, [ebp+arg_4]
0x40566d  test    ebx, ebx
0x40566f  jz      loc_405751
0x405675  cmp     dword ptr [ebx+328h], 0
0x40567c  jnz     loc_405751
0x405682  mov     eax, [edi+24h]
0x405685  mov     cx, [esi]
0x405688  cmp     cx, [eax]
0x40568b  jnz     short loc_4056AB
0x40568d  test    cx, cx
0x405690  jz      short loc_4056A7
0x405692  mov     cx, [esi+2]
0x405696  cmp     cx, [eax+2]
0x40569a  jnz     short loc_4056AB
0x40569c  add     esi, 4
0x40569f  add     eax, 4
0x4056a2  test    cx, cx
0x4056a5  jnz     short loc_405685
0x4056a7  xor     eax, eax
0x4056a9  jmp     short loc_4056B0
0x4056ab  sbb     eax, eax
0x4056ad  or      eax, 1
0x4056b0  test    eax, eax
0x4056b2  jz      short loc_4056BE
0x4056b4  mov     esi, 80070005h
0x4056b9  jmp     loc_405756
0x4056be  push    ecx; int
0x4056bf  push    [ebp+this]; char *
0x4056c2  mov     ecx, edi; this
0x4056c4  call    ?FileIsAuthorized@CActiveXInstallBroker@@AAEJPBDH@Z; CActiveXInstallBroker::FileIsAuthorized(char const *,int)
0x4056c9  mov     esi, eax
0x4056cb  test    esi, esi
0x4056cd  js      loc_405756
0x4056d3  lea     ecx, [ebx+1Ch]
0x4056d6  call    ?CreateTempDir@@YGJPADK@Z; CreateTempDir(char *,ulong)
0x4056db  mov     esi, eax
0x4056dd  test    esi, esi
0x4056df  js      short loc_405756
0x4056e1  lea     eax, [ebp+pv]
0x4056e4  mov     [ebp+pv], 0
0x4056eb  push    eax; unsigned int
0x4056ec  lea     edx, [ebx+1Ch]
0x4056ef  call    ?SZtoWSZ@@YGJIPBDPAPAG@Z; SZtoWSZ(uint,char const *,ushort * *)
0x4056f4  mov     esi, eax
0x4056f6  test    esi, esi
0x4056f8  js      short loc_405756
0x4056fa  cmp     dword ptr [edi+54h], 0
0x4056fe  jnz     short loc_40570C
0x405700  mov     ecx, [ebp+pv]
0x405703  call    ?ContainingPathIsTamperProof@@YGHPBG@Z; ContainingPathIsTamperProof(ushort const *)
0x405708  test    eax, eax
0x40570a  jz      short loc_4056B4
0x40570c  push    [ebp+pv]; pv
0x40570f  call    ds:__imp__CoTaskMemFree@4; CoTaskMemFree(x)
0x405715  push    [ebp+this]
0x405718  push    ebx
0x405719  call    ds:__imp__Extract@8; Extract(x,x)
0x40571f  mov     esi, eax
0x405721  test    esi, esi
0x405723  js      short loc_405756
0x405725  mov     edx, [ebx+10h]
0x405728  lea     eax, [edi+4Ch]
0x40572b  push    eax; char *
0x40572c  lea     ecx, [ebx+1Ch]
0x40572f  call    ?AddFilesToFileList@@YGJPBDPAUsFNAME@@PAPAU1@@Z; AddFilesToFileList(char const *,sFNAME *,sFNAME * *)
0x405734  mov     esi, eax
0x405736  test    esi, esi
0x405738  js      short loc_405756
0x40573a  mov     ecx, [edi+4Ch]
0x40573d  call    ?SetFileListIntegrityLevel@@YGJPAUsFNAME@@H@Z; SetFileListIntegrityLevel(sFNAME *,int)
0x405742  mov     esi, eax
0x405744  test    esi, esi
0x405746  js      short loc_405756
0x405748  mov     dword ptr [edi+1Ch], 3
0x40574f  jmp     short loc_405756
0x405751  mov     esi, 80070057h
0x405756  mov     ecx, edi; this
0x405758  call    ?Unlock@CLock@@QAEHXZ; CLock::Unlock(void)
0x40575d  pop     edi
0x40575e  mov     eax, esi
0x405760  pop     esi
0x405761  pop     ebx
0x405762  leave
0x405763  retn    8
```
