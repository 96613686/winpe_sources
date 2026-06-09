# IsInFileListA(char const *,sFNAME *)

- ea: `0x406f2f`
- end: `0x406fd6`
- name: `?IsInFileListA@@YGHPBDPAUsFNAME@@@Z`
- size: `167`
- prototype: `int __fastcall(char *, int)`
- caller_count: `4`
- callee_count: `4`
- tags: ``

## callers

- `0x403094`
- `0x4058f8`
- `0x406e8a`
- `0x406fdc`

## callees

- `0x406266`
- `0x406f2f`
- `0x40cb60`
- `0x40eb27`

## import_xrefs

- `KERNEL32!lstrcmpiA` at `0x406faf`
- `KERNEL32!lstrcmpiA` at `0x406faf`

## pseudocode

```c
int __fastcall IsInFileListA(char *a1, int a2)
{
  int v2; // ebx
  unsigned int *v5; // [esp+0h] [ebp-114h]
  unsigned int v6; // [esp+4h] [ebp-110h]
  CHAR String1[260]; // [esp+Ch] [ebp-108h] BYREF

  v2 = 0;
  memset(String1, 0, sizeof(String1));
  if ( StringCchCopyExA(a1, 0, 0, (char **)0x100, v5, v6) >= 0 )
  {
    while ( a2 )
    {
      if ( *(_DWORD *)a2 && !lstrcmpiA(String1, *(LPCSTR *)a2) )
        return 1;
      a2 = *(_DWORD *)(a2 + 4);
    }
  }
  return v2;
}

```

## disassembly

```asm
0x406f2f  mov     edi, edi
0x406f31  push    ebp
0x406f32  mov     ebp, esp
0x406f34  sub     esp, 108h
0x406f3a  mov     eax, ___security_cookie
0x406f3f  xor     eax, ebp
0x406f41  mov     [ebp+var_4], eax
0x406f44  push    ebx
0x406f45  push    esi; unsigned int
0x406f46  push    edi; unsigned int *
0x406f47  xor     ebx, ebx
0x406f49  lea     eax, [ebp+var_107]
0x406f4f  push    103h; Size
0x406f54  push    ebx; Val
0x406f55  push    eax; void *
0x406f56  mov     edi, edx
0x406f58  mov     [ebp+String1], bl
0x406f5e  mov     esi, ecx
0x406f60  call    _memset
0x406f65  add     esp, 0Ch
0x406f68  lea     ecx, [ebp+String1]
0x406f6e  mov     edx, 104h
0x406f73  push    100h; char **
0x406f78  push    ebx; char *
0x406f79  push    ebx; unsigned int
0x406f7a  push    esi; char *
0x406f7b  call    ?StringCchCopyExA@@YGJPADIPBDPAPADPAIK@Z; StringCchCopyExA(char *,uint,char const *,char * *,uint *,ulong)
0x406f80  test    eax, eax
0x406f82  js      short loc_406FC5
0x406f84  mov     al, [ebp+String1]
0x406f8a  lea     ecx, [ebp+String1]
0x406f90  jmp     short loc_406F9C
0x406f92  cmp     al, 2Fh ; '/'
0x406f94  jnz     short loc_406F99
0x406f96  mov     byte ptr [ecx], 5Ch ; '\'
0x406f99  inc     ecx
0x406f9a  mov     al, [ecx]
0x406f9c  test    al, al
0x406f9e  jnz     short loc_406F92
0x406fa0  jmp     short loc_406FBC
0x406fa2  cmp     [edi], ebx
0x406fa4  jz      short loc_406FB9
0x406fa6  push    dword ptr [edi]; lpString2
0x406fa8  lea     eax, [ebp+String1]
0x406fae  push    eax; lpString1
0x406faf  call    ds:__imp__lstrcmpiA@8; lstrcmpiA(x,x)
0x406fb5  test    eax, eax
0x406fb7  jz      short loc_406FC2
0x406fb9  mov     edi, [edi+4]
0x406fbc  test    edi, edi
0x406fbe  jnz     short loc_406FA2
0x406fc0  jmp     short loc_406FC5
0x406fc2  xor     ebx, ebx
0x406fc4  inc     ebx
0x406fc5  mov     ecx, [ebp+var_4]
0x406fc8  mov     eax, ebx
0x406fca  pop     edi
0x406fcb  pop     esi
0x406fcc  xor     ecx, ebp; StackCookie
0x406fce  pop     ebx
0x406fcf  call    @__security_check_cookie@4; __security_check_cookie(x)
0x406fd4  leave
0x406fd5  retn
```
