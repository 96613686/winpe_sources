# CActiveXInstallBroker::DeleteExtractedFile(char const *)

- ea: `0x4058f8`
- end: `0x405960`
- name: `?DeleteExtractedFile@CActiveXInstallBroker@@QAGJPBD@Z`
- size: `104`
- prototype: `int __fastcall(int *, const CHAR *)`
- caller_count: `1`
- callee_count: `4`
- tags: `file_ops, installer_update, broker_com_uri`

## callers

- `0x406160`

## callees

- `0x402eb9`
- `0x402ed3`
- `0x4058f8`
- `0x406f2f`

## import_xrefs

- `KERNEL32!SetFileAttributesA` at `0x405946`
- `KERNEL32!SetFileAttributesA` at `0x405946`
- `KERNEL32!DeleteFileA` at `0x40594d`
- `KERNEL32!DeleteFileA` at `0x40594d`

## pseudocode

```c
int __fastcall CActiveXInstallBroker::DeleteExtractedFile(int *a1, const CHAR *a2)
{
  int v4; // esi
  const char *v6; // [esp+0h] [ebp-Ch]
  struct sFNAME *v7; // [esp+4h] [ebp-8h]

  v4 = 0;
  if ( CLock::Lock((CLock *)a1) )
  {
    if ( a1[7] >= 4 )
    {
      if ( a2 )
      {
        if ( IsInFileListA(v6, v7) )
        {
          SetFileAttributesA(a2, 0x80u);
          DeleteFileA(a2);
        }
        else
        {
          v4 = -2147024891;
        }
      }
      else
      {
        v4 = -2147024809;
      }
    }
    else
    {
      v4 = -2147019873;
    }
  }
  else
  {
    v4 = -2147024882;
  }
  CLock::Unlock((CLock *)a1);
  return v4;
}

```

## disassembly

```asm
0x4058f8  mov     edi, edi
0x4058fa  push    ebx
0x4058fb  push    esi; struct sFNAME *
0x4058fc  push    edi; char *
0x4058fd  mov     edi, edx
0x4058ff  mov     ebx, ecx
0x405901  xor     esi, esi
0x405903  call    ?Lock@CLock@@QAEHXZ; CLock::Lock(void)
0x405908  test    eax, eax
0x40590a  jnz     short loc_405913
0x40590c  mov     esi, 8007000Eh
0x405911  jmp     short loc_405953
0x405913  cmp     dword ptr [ebx+1Ch], 4
0x405917  jge     short loc_405920
0x405919  mov     esi, 8007139Fh
0x40591e  jmp     short loc_405953
0x405920  test    edi, edi
0x405922  jnz     short loc_40592B
0x405924  mov     esi, 80070057h
0x405929  jmp     short loc_405953
0x40592b  mov     edx, [ebx+4Ch]
0x40592e  mov     ecx, edi
0x405930  call    ?IsInFileListA@@YGHPBDPAUsFNAME@@@Z; IsInFileListA(char const *,sFNAME *)
0x405935  test    eax, eax
0x405937  jnz     short loc_405940
0x405939  mov     esi, 80070005h
0x40593e  jmp     short loc_405953
0x405940  push    80h; dwFileAttributes
0x405945  push    edi; lpFileName
0x405946  call    ds:__imp__SetFileAttributesA@8; SetFileAttributesA(x,x)
0x40594c  push    edi; lpFileName
0x40594d  call    ds:__imp__DeleteFileA@4; DeleteFileA(x)
0x405953  mov     ecx, ebx; this
0x405955  call    ?Unlock@CLock@@QAEHXZ; CLock::Unlock(void)
0x40595a  pop     edi
0x40595b  mov     eax, esi
0x40595d  pop     esi
0x40595e  pop     ebx
0x40595f  retn
```
