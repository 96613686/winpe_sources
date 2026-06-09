# CActiveXInstallBroker::RemoveExtractedFilesAndDirs(ushort *,sSESSION *)

- ea: `0x405849`
- end: `0x4058f2`
- name: `?RemoveExtractedFilesAndDirs@CActiveXInstallBroker@@QAGJPAGPAUsSESSION@@@Z`
- size: `169`
- prototype: `int __userpurge@<eax>(const unsigned __int16 *@<edx>, int@<ecx>, CActiveXInstallBroker *this, unsigned __int16 *, struct sSESSION *)`
- caller_count: `1`
- callee_count: `6`
- tags: `file_ops, installer_update, broker_com_uri`

## callers

- `0x4060a0`

## callees

- `0x402eb9`
- `0x402ed3`
- `0x405849`
- `0x406fdc`
- `0x40723a`
- `0x4072e3`

## pseudocode

```c
int __userpurge CActiveXInstallBroker::RemoveExtractedFilesAndDirs@<eax>(
        const unsigned __int16 *a1@<edx>,
        int a2@<ecx>,
        CActiveXInstallBroker *this,
        unsigned __int16 *a4,
        struct sSESSION *a5)
{
  int v7; // esi
  int v8; // eax
  struct sSESSION *v10; // [esp+0h] [ebp-Ch]
  struct sFNAME *v11; // [esp+4h] [ebp-8h]

  v7 = 0;
  if ( CLock::Lock((CLock *)a2) )
  {
    if ( *(int *)(a2 + 28) >= 4 )
    {
      if ( a1 )
      {
        v8 = wcscmp(a1, *(const unsigned __int16 **)(a2 + 36));
        if ( v8 )
          v8 = v8 < 0 ? -1 : 1;
        if ( v8 || !FilesInFileList(v10, v11) )
        {
          v7 = -2147024891;
        }
        else if ( DeleteExtractedFiles((char *)this + 28, *((_DWORD *)this + 4)) >= 0 )
        {
          v7 = RemoveDirectoryAndChildren((const char *)this + 28);
        }
      }
      else
      {
        v7 = -2147024809;
      }
    }
    else
    {
      v7 = -2147019873;
    }
  }
  else
  {
    v7 = -2147024882;
  }
  CLock::Unlock((CLock *)a2);
  return v7;
}

```

## disassembly

```asm
0x405849  mov     edi, edi
0x40584b  push    ebp
0x40584c  mov     ebp, esp
0x40584e  push    ebx
0x40584f  push    esi; struct sFNAME *
0x405850  push    edi; char *
0x405851  mov     edi, edx
0x405853  mov     ebx, ecx
0x405855  xor     esi, esi
0x405857  call    ?Lock@CLock@@QAEHXZ; CLock::Lock(void)
0x40585c  test    eax, eax
0x40585e  jnz     short loc_405867
0x405860  mov     esi, 8007000Eh
0x405865  jmp     short loc_4058E2
0x405867  cmp     dword ptr [ebx+1Ch], 4
0x40586b  jge     short loc_405874
0x40586d  mov     esi, 8007139Fh
0x405872  jmp     short loc_4058E2
0x405874  test    edi, edi
0x405876  jnz     short loc_40587F
0x405878  mov     esi, 80070057h
0x40587d  jmp     short loc_4058E2
0x40587f  mov     eax, [ebx+24h]
0x405882  mov     cx, [edi]
0x405885  cmp     cx, [eax]
0x405888  jnz     short loc_4058A8
0x40588a  test    cx, cx
0x40588d  jz      short loc_4058A4
0x40588f  mov     cx, [edi+2]
0x405893  cmp     cx, [eax+2]
0x405897  jnz     short loc_4058A8
0x405899  add     edi, 4
0x40589c  add     eax, 4
0x40589f  test    cx, cx
0x4058a2  jnz     short loc_405882
0x4058a4  xor     eax, eax
0x4058a6  jmp     short loc_4058AD
0x4058a8  sbb     eax, eax
0x4058aa  or      eax, 1
0x4058ad  test    eax, eax
0x4058af  jz      short loc_4058B8
0x4058b1  mov     esi, 80070005h
0x4058b6  jmp     short loc_4058E2
0x4058b8  mov     edi, [ebp+this]
0x4058bb  mov     ecx, edi
0x4058bd  mov     edx, [ebx+4Ch]
0x4058c0  call    ?FilesInFileList@@YGHPAUsSESSION@@PAUsFNAME@@@Z; FilesInFileList(sSESSION *,sFNAME *)
0x4058c5  test    eax, eax
0x4058c7  jz      short loc_4058B1
0x4058c9  mov     edx, [edi+10h]
0x4058cc  lea     ecx, [edi+1Ch]
0x4058cf  call    ?DeleteExtractedFiles@@YGJPADPAUsFNAME@@@Z; DeleteExtractedFiles(char *,sFNAME *)
0x4058d4  test    eax, eax
0x4058d6  js      short loc_4058E2
0x4058d8  lea     ecx, [edi+1Ch]
0x4058db  call    ?RemoveDirectoryAndChildren@@YGJPBD@Z; RemoveDirectoryAndChildren(char const *)
0x4058e0  mov     esi, eax
0x4058e2  mov     ecx, ebx; this
0x4058e4  call    ?Unlock@CLock@@QAEHXZ; CLock::Unlock(void)
0x4058e9  pop     edi
0x4058ea  mov     eax, esi
0x4058ec  pop     esi
0x4058ed  pop     ebx
0x4058ee  pop     ebp
0x4058ef  retn    4
```
