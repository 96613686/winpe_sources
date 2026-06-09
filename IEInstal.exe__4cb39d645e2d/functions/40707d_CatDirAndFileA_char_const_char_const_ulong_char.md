# CatDirAndFileA(char const *,char const *,ulong,char *)

- ea: `0x40707d`
- end: `0x40713c`
- name: `?CatDirAndFileA@@YGHPBD0KPAD@Z`
- size: `191`
- prototype: `int __userpurge@<eax>(char *@<edx>, char *@<ecx>, const char *, char *, unsigned int, char *)`
- caller_count: `4`
- callee_count: `5`
- tags: ``

## callers

- `0x406e8a`
- `0x406fdc`
- `0x407142`
- `0x40723a`

## callees

- `0x406224`
- `0x40646b`
- `0x40707d`
- `0x40829a`
- `0x408373`

## pseudocode

```c
int __userpurge CatDirAndFileA@<eax>(
        char *a1@<edx>,
        char *a2@<ecx>,
        const char *a3,
        char *a4,
        unsigned int a5,
        char *a6)
{
  const char *v6; // ebx
  unsigned int v7; // esi
  char v8; // al
  char *v10; // [esp+0h] [ebp-14h]

  v6 = a3;
  v7 = 0;
  if ( !a3 )
    return 0;
  *a4 = 0;
  if ( a2 )
    v7 = strlen(a2);
  if ( AxiPreScanPathA(a1) < 0 || AxiPreScanPathA(a2) < 0 )
    return 0;
  if ( v7 )
  {
    v6 = &a3[-v7];
    if ( (int)&a3[-v7] <= 1 || StringCchCopyA(a4, (unsigned int)a3, (size_t)a2) < 0 )
      return 0;
    v8 = a4[v7 - 1];
    if ( v8 && v8 != 92 && v8 != 58 )
    {
      *(_WORD *)&a4[v7] = 92;
      --v6;
    }
  }
  if ( *a1 && (int)&v6[-strlen(a1)] > 0 && StringCchCatA(a4, (unsigned int)a3, a1) >= 0 )
  {
    AxiAdjustSlashToBackslashA(v10);
    return 1;
  }
  return 0;
}

```

## disassembly

```asm
0x40707d  mov     edi, edi
0x40707f  push    ebp
0x407080  mov     ebp, esp
0x407082  push    ecx
0x407083  push    ecx
0x407084  push    ebx
0x407085  mov     ebx, [ebp+arg_0]
0x407088  mov     eax, ecx
0x40708a  push    esi
0x40708b  xor     esi, esi
0x40708d  mov     [ebp+var_8], edx
0x407090  mov     [ebp+cchDest], eax
0x407093  push    edi; char *
0x407094  test    ebx, ebx
0x407096  jbe     loc_407133
0x40709c  mov     edi, [ebp+arg_4]
0x40709f  mov     byte ptr [edi], 0
0x4070a2  test    eax, eax
0x4070a4  jz      short loc_4070B4
0x4070a6  mov     esi, eax
0x4070a8  lea     ecx, [esi+1]
0x4070ab  mov     al, [esi]
0x4070ad  inc     esi
0x4070ae  test    al, al
0x4070b0  jnz     short loc_4070AB
0x4070b2  sub     esi, ecx
0x4070b4  mov     ecx, edx
0x4070b6  call    ?AxiPreScanPathA@@YGJPBD@Z; AxiPreScanPathA(char const *)
0x4070bb  test    eax, eax
0x4070bd  js      short loc_407133
0x4070bf  mov     ecx, [ebp+cchDest]
0x4070c2  call    ?AxiPreScanPathA@@YGJPBD@Z; AxiPreScanPathA(char const *)
0x4070c7  test    eax, eax
0x4070c9  js      short loc_407133
0x4070cb  test    esi, esi
0x4070cd  jz      short loc_4070FD
0x4070cf  sub     ebx, esi
0x4070d1  cmp     ebx, 1
0x4070d4  jle     short loc_407133
0x4070d6  push    [ebp+cchDest]; cchDest
0x4070d9  push    [ebp+arg_0]; unsigned int
0x4070dc  push    edi; char *
0x4070dd  call    ?StringCchCopyA@@YGJPADIPBD@Z; StringCchCopyA(char *,uint,char const *)
0x4070e2  test    eax, eax
0x4070e4  js      short loc_407133
0x4070e6  mov     al, [esi+edi-1]
0x4070ea  test    al, al
0x4070ec  jz      short loc_4070FD
0x4070ee  cmp     al, 5Ch ; '\'
0x4070f0  jz      short loc_4070FD
0x4070f2  cmp     al, 3Ah ; ':'
0x4070f4  jz      short loc_4070FD
0x4070f6  mov     word ptr [esi+edi], 5Ch ; '\'
0x4070fc  dec     ebx
0x4070fd  mov     edx, [ebp+var_8]
0x407100  cmp     byte ptr [edx], 0
0x407103  jz      short loc_407133
0x407105  mov     ecx, edx
0x407107  lea     esi, [ecx+1]
0x40710a  mov     al, [ecx]
0x40710c  inc     ecx
0x40710d  test    al, al
0x40710f  jnz     short loc_40710A
0x407111  sub     ecx, esi
0x407113  sub     ebx, ecx
0x407115  test    ebx, ebx
0x407117  jle     short loc_407133
0x407119  push    edx; char *
0x40711a  push    [ebp+arg_0]; unsigned int
0x40711d  push    edi; char *
0x40711e  call    ?StringCchCatA@@YGJPADIPBD@Z; StringCchCatA(char *,uint,char const *)
0x407123  test    eax, eax
0x407125  js      short loc_407133
0x407127  mov     ecx, edi
0x407129  call    ?AxiAdjustSlashToBackslashA@@YGXPAD@Z; AxiAdjustSlashToBackslashA(char *)
0x40712e  xor     eax, eax
0x407130  inc     eax
0x407131  jmp     short loc_407135
0x407133  xor     eax, eax
0x407135  pop     edi
0x407136  pop     esi
0x407137  pop     ebx
0x407138  leave
0x407139  retn    8
```
