# StringCchCopyExA(char *,uint,char const *,char * *,uint *,ulong)

- ea: `0x406266`
- end: `0x4063a9`
- name: `?StringCchCopyExA@@YGJPADIPBDPAPADPAIK@Z`
- size: `323`
- prototype: `int __userpurge@<eax>(size_t@<edx>, _BYTE *@<ecx>, char *cchDest, _DWORD *, char *, STRSAFE_LPSTR *ppszDestEnd, unsigned int *, unsigned int)`
- caller_count: `2`
- callee_count: `4`
- tags: ``

## callers

- `0x406f2f`
- `0x407fd4`

## callees

- `0x406266`
- `0x406568`
- `0x40663b`
- `0x40eb27`

## pseudocode

```c
int __userpurge StringCchCopyExA@<eax>(
        size_t a1@<edx>,
        _BYTE *a2@<ecx>,
        char *cchDest,
        _DWORD *a4,
        char *a5,
        STRSAFE_LPSTR *ppszDestEnd,
        unsigned int *a7,
        unsigned int a8)
{
  int v9; // esi
  STRSAFE_LPSTR *v10; // ecx
  size_t v12; // ebx
  const unsigned __int16 *v13; // edx
  _BYTE *v14; // edx
  HRESULT v15; // eax
  size_t v16; // ecx
  char *v18; // [esp+0h] [ebp-18h]
  size_t v19; // [esp+4h] [ebp-14h]
  _BYTE *v20; // [esp+Ch] [ebp-Ch]
  size_t cchOriginalDestLength; // [esp+10h] [ebp-8h] BYREF
  char pszDest[4]; // [esp+14h] [ebp-4h] BYREF

  v9 = 0;
  v10 = ppszDestEnd;
  v20 = a2;
  if ( ((unsigned __int16)ppszDestEnd & 0x100) != 0 )
  {
    if ( a2 || !a1 )
    {
LABEL_6:
      if ( a1 <= 0x7FFFFFFF )
        goto LABEL_8;
    }
  }
  else
  {
    v9 = 0;
    if ( a1 )
      goto LABEL_6;
  }
  v9 = -2147024809;
LABEL_8:
  if ( v9 < 0 )
  {
    if ( a1 )
      *a2 = 0;
    return v9;
  }
  *(_DWORD *)pszDest = a2;
  v12 = a1;
  cchOriginalDestLength = a1;
  if ( ((unsigned __int16)ppszDestEnd & 0x100) != 0 )
  {
    v13 = &Args;
    if ( cchDest )
      v13 = (const unsigned __int16 *)cchDest;
  }
  else
  {
    v13 = (const unsigned __int16 *)cchDest;
  }
  v9 = 0;
  if ( ((unsigned int)ppszDestEnd & 0xFFFFE000) != 0 )
  {
    v9 = -2147024809;
    if ( a1 )
      *a2 = 0;
    goto LABEL_17;
  }
  if ( a1 )
  {
    cchOriginalDestLength = 0;
    v15 = StringCopyWorkerA((STRSAFE_LPSTR)&cchOriginalDestLength, (size_t)v13, (size_t *)ppszDestEnd, v18, v19);
    v16 = cchOriginalDestLength;
    v9 = v15;
    v12 = a1 - cchOriginalDestLength;
    cchOriginalDestLength = a1 - cchOriginalDestLength;
    v14 = &v20[v16];
    v10 = ppszDestEnd;
    *(_DWORD *)pszDest = v14;
    if ( v15 < 0 )
      goto LABEL_17;
    if ( ((unsigned __int16)ppszDestEnd & 0x200) == 0 || v12 <= 1 )
      goto LABEL_23;
    memset(v14 + 1, (unsigned __int8)ppszDestEnd, v12 - 1);
LABEL_22:
    v14 = *(_BYTE **)pszDest;
LABEL_23:
    if ( a4 )
      *a4 = v14;
    if ( a5 )
      *(_DWORD *)a5 = v12;
    return v9;
  }
  if ( !*(_BYTE *)v13 )
    goto LABEL_22;
  v9 = -2147024774;
  if ( !a2 )
    v9 = -2147024809;
LABEL_17:
  if ( ((unsigned __int16)v10 & 0x1C00) != 0 && a1 )
  {
    StringExHandleOtherFlagsA(pszDest, (size_t)pszDest, (size_t)&cchOriginalDestLength, v10, (size_t *)v18, v19);
    v12 = cchOriginalDestLength;
  }
  if ( v9 >= 0 || v9 == -2147024774 )
    goto LABEL_22;
  return v9;
}

```

## disassembly

```asm
0x406266  mov     edi, edi
0x406268  push    ebp
0x406269  mov     ebp, esp
0x40626b  sub     esp, 0Ch
0x40626e  push    ebx
0x40626f  push    esi; dwFlags
0x406270  mov     eax, ecx
0x406272  xor     esi, esi
0x406274  mov     ecx, [ebp+ppszDestEnd]
0x406277  mov     ebx, 80070057h
0x40627c  push    edi; pcchRemaining
0x40627d  mov     edi, edx
0x40627f  mov     [ebp+var_C], eax
0x406282  mov     edx, ecx
0x406284  and     edx, 100h
0x40628a  jz      short loc_406296
0x40628c  test    eax, eax
0x40628e  jnz     short loc_40629C
0x406290  test    edi, edi
0x406292  jnz     short loc_4062A4
0x406294  jmp     short loc_40629C
0x406296  xor     esi, esi
0x406298  test    edi, edi
0x40629a  jz      short loc_4062A4
0x40629c  cmp     edi, 7FFFFFFFh
0x4062a2  jbe     short loc_4062A6
0x4062a4  mov     esi, ebx
0x4062a6  test    esi, esi
0x4062a8  js      loc_406399
0x4062ae  mov     dword ptr [ebp+pszDest], eax
0x4062b1  mov     ebx, edi
0x4062b3  mov     [ebp+cchOriginalDestLength], ebx
0x4062b6  test    edx, edx
0x4062b8  jz      short loc_4062C9
0x4062ba  cmp     [ebp+cchDest], 0
0x4062be  mov     edx, offset Args
0x4062c3  cmovnz  edx, [ebp+cchDest]
0x4062c7  jmp     short loc_4062CC
0x4062c9  mov     edx, [ebp+cchDest]
0x4062cc  xor     esi, esi
0x4062ce  test    ecx, 0FFFFE000h
0x4062d4  jz      short loc_40632B
0x4062d6  mov     esi, 80070057h
0x4062db  test    edi, edi
0x4062dd  jz      short loc_4062E2
0x4062df  mov     byte ptr [eax], 0
0x4062e2  test    ecx, 1C00h
0x4062e8  jz      short loc_406304
0x4062ea  test    edi, edi
0x4062ec  jz      short loc_406304
0x4062ee  push    ecx; ppszDestEnd
0x4062ef  lea     ecx, [ebp+cchOriginalDestLength]
0x4062f2  mov     edx, edi
0x4062f4  push    ecx; cchOriginalDestLength
0x4062f5  lea     ecx, [ebp+pszDest]
0x4062f8  push    ecx; cbDest
0x4062f9  push    ecx; pszDest
0x4062fa  mov     ecx, eax
0x4062fc  call    StringExHandleOtherFlagsA
0x406301  mov     ebx, [ebp+cchOriginalDestLength]
0x406304  test    esi, esi
0x406306  jns     short loc_406314
0x406308  cmp     esi, 8007007Ah
0x40630e  jnz     loc_4063A0
0x406314  mov     edx, dword ptr [ebp+pszDest]
0x406317  mov     eax, [ebp+arg_4]
0x40631a  test    eax, eax
0x40631c  jz      short loc_406320
0x40631e  mov     [eax], edx
0x406320  mov     eax, [ebp+arg_8]
0x406323  test    eax, eax
0x406325  jz      short loc_4063A0
0x406327  mov     [eax], ebx
0x406329  jmp     short loc_4063A0
0x40632b  test    edi, edi
0x40632d  jnz     short loc_406343
0x40632f  cmp     byte ptr [edx], 0
0x406332  jz      short loc_406314
0x406334  mov     esi, 8007007Ah
0x406339  test    eax, eax
0x40633b  lea     edx, [esi-23h]
0x40633e  cmovz   esi, edx
0x406341  jmp     short loc_4062E2
0x406343  push    ecx; pcchNewDestLength
0x406344  push    edx; cchDest
0x406345  lea     ecx, [ebp+cchOriginalDestLength]
0x406348  mov     [ebp+cchOriginalDestLength], esi
0x40634b  push    ecx; pszDest
0x40634c  mov     edx, edi
0x40634e  mov     ecx, eax
0x406350  call    StringCopyWorkerA
0x406355  mov     ecx, [ebp+cchOriginalDestLength]
0x406358  mov     esi, eax
0x40635a  mov     eax, [ebp+var_C]
0x40635d  sub     ebx, ecx
0x40635f  mov     [ebp+cchOriginalDestLength], ebx
0x406362  lea     edx, [ecx+eax]
0x406365  mov     ecx, [ebp+ppszDestEnd]
0x406368  mov     dword ptr [ebp+pszDest], edx
0x40636b  test    esi, esi
0x40636d  js      loc_4062E2
0x406373  test    ecx, 200h
0x406379  jz      short loc_406317
0x40637b  cmp     ebx, 1
0x40637e  jbe     short loc_406317
0x406380  lea     eax, [ebx-1]
0x406383  push    eax; Size
0x406384  movzx   eax, cl
0x406387  push    eax; Val
0x406388  lea     eax, [edx+1]
0x40638b  push    eax; void *
0x40638c  call    _memset
0x406391  add     esp, 0Ch
0x406394  jmp     loc_406314
0x406399  test    edi, edi
0x40639b  jz      short loc_4063A0
0x40639d  mov     byte ptr [eax], 0
0x4063a0  pop     edi
0x4063a1  mov     eax, esi
0x4063a3  pop     esi
0x4063a4  pop     ebx
0x4063a5  leave
0x4063a6  retn    10h
```
