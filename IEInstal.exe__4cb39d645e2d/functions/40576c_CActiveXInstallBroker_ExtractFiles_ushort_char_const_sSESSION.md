# CActiveXInstallBroker::ExtractFiles(ushort *,char const *,sSESSION *)

- ea: `0x40576c`
- end: `0x405843`
- name: `?ExtractFiles@CActiveXInstallBroker@@QAGJPAGPBDPAUsSESSION@@@Z`
- size: `215`
- prototype: `int __userpurge@<eax>(_WORD *@<edx>, CActiveXInstallBroker *@<ecx>, CActiveXInstallBroker *this, unsigned __int16 *, const char *, struct sSESSION *)`
- caller_count: `1`
- callee_count: `5`
- tags: `file_ops, installer_update, broker_com_uri`

## callers

- `0x406070`

## callees

- `0x402eb9`
- `0x402ed3`
- `0x40304d`
- `0x40576c`
- `0x407561`

## import_xrefs

- `urlmon!Extract` at `0x40580b`
- `urlmon!Extract` at `0x40580b`

## pseudocode

```c
int __userpurge CActiveXInstallBroker::ExtractFiles@<eax>(
        _WORD *a1@<edx>,
        CActiveXInstallBroker *a2@<ecx>,
        CActiveXInstallBroker *this,
        unsigned __int16 *a4,
        const char *a5,
        struct sSESSION *a6)
{
  int v8; // ecx
  int IsAuthorized; // esi
  _WORD *v10; // eax
  bool v11; // cf
  int v12; // eax
  struct sFNAME *v14; // [esp+0h] [ebp-Ch]
  int v15; // [esp+4h] [ebp-8h]

  if ( CLock::Lock(a2) )
  {
    if ( *((int *)a2 + 7) >= 3 )
    {
      if ( a1 && this && a4 && *((_DWORD *)a4 + 202) )
      {
        v10 = (_WORD *)*((_DWORD *)a2 + 9);
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
          IsAuthorized = -2147024891;
        }
        else
        {
          IsAuthorized = CActiveXInstallBroker::FileIsAuthorized(a2, (const char *)this, v8);
          if ( IsAuthorized >= 0 )
          {
            IsAuthorized = Extract(a4, this);
            if ( IsAuthorized >= 0 )
            {
              IsAuthorized = SetFileListIntegrityLevel(v14, v15);
              if ( IsAuthorized >= 0 )
                *((_DWORD *)a2 + 7) = 4;
            }
          }
        }
      }
      else
      {
        IsAuthorized = -2147024809;
      }
    }
    else
    {
      IsAuthorized = -2147019873;
    }
  }
  else
  {
    IsAuthorized = -2147024882;
  }
  CLock::Unlock(a2);
  return IsAuthorized;
}

```

## disassembly

```asm
0x40576c  mov     edi, edi
0x40576e  push    ebp
0x40576f  mov     ebp, esp
0x405771  push    ebx
0x405772  push    esi; int
0x405773  push    edi; struct sFNAME *
0x405774  mov     esi, edx
0x405776  mov     edi, ecx
0x405778  call    ?Lock@CLock@@QAEHXZ; CLock::Lock(void)
0x40577d  test    eax, eax
0x40577f  jnz     short loc_40578B
0x405781  mov     esi, 8007000Eh
0x405786  jmp     loc_405833
0x40578b  cmp     dword ptr [edi+1Ch], 3
0x40578f  jge     short loc_40579B
0x405791  mov     esi, 8007139Fh
0x405796  jmp     loc_405833
0x40579b  test    esi, esi
0x40579d  jz      loc_40582E
0x4057a3  cmp     [ebp+this], 0
0x4057a7  jz      loc_40582E
0x4057ad  mov     ebx, [ebp+arg_4]
0x4057b0  test    ebx, ebx
0x4057b2  jz      short loc_40582E
0x4057b4  cmp     dword ptr [ebx+328h], 0
0x4057bb  jz      short loc_40582E
0x4057bd  mov     eax, [edi+24h]
0x4057c0  mov     cx, [esi]
0x4057c3  cmp     cx, [eax]
0x4057c6  jnz     short loc_4057E6
0x4057c8  test    cx, cx
0x4057cb  jz      short loc_4057E2
0x4057cd  mov     cx, [esi+2]
0x4057d1  cmp     cx, [eax+2]
0x4057d5  jnz     short loc_4057E6
0x4057d7  add     esi, 4
0x4057da  add     eax, 4
0x4057dd  test    cx, cx
0x4057e0  jnz     short loc_4057C0
0x4057e2  xor     eax, eax
0x4057e4  jmp     short loc_4057EB
0x4057e6  sbb     eax, eax
0x4057e8  or      eax, 1
0x4057eb  test    eax, eax
0x4057ed  jz      short loc_4057F6
0x4057ef  mov     esi, 80070005h
0x4057f4  jmp     short loc_405833
0x4057f6  push    ecx; int
0x4057f7  push    [ebp+this]; char *
0x4057fa  mov     ecx, edi; this
0x4057fc  call    ?FileIsAuthorized@CActiveXInstallBroker@@AAEJPBDH@Z; CActiveXInstallBroker::FileIsAuthorized(char const *,int)
0x405801  mov     esi, eax
0x405803  test    esi, esi
0x405805  js      short loc_405833
0x405807  push    [ebp+this]
0x40580a  push    ebx
0x40580b  call    ds:__imp__Extract@8; Extract(x,x)
0x405811  mov     esi, eax
0x405813  test    esi, esi
0x405815  js      short loc_405833
0x405817  mov     ecx, [edi+4Ch]
0x40581a  call    ?SetFileListIntegrityLevel@@YGJPAUsFNAME@@H@Z; SetFileListIntegrityLevel(sFNAME *,int)
0x40581f  mov     esi, eax
0x405821  test    esi, esi
0x405823  js      short loc_405833
0x405825  mov     dword ptr [edi+1Ch], 4
0x40582c  jmp     short loc_405833
0x40582e  mov     esi, 80070057h
0x405833  mov     ecx, edi; this
0x405835  call    ?Unlock@CLock@@QAEHXZ; CLock::Unlock(void)
0x40583a  pop     edi
0x40583b  mov     eax, esi
0x40583d  pop     esi
0x40583e  pop     ebx
0x40583f  pop     ebp
0x405840  retn    8
```
