# GetCompositeMlKemBlobInfo

- ea: `0x180063fdc`
- end: `0x18006408c`
- name: `GetCompositeMlKemBlobInfo`
- size: `176`
- prototype: `__int64 __fastcall(char *, wchar_t ***)`
- caller_count: `2`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180063c20`
- `0x1800642d4`

## callees

- `0x18000ecb0`
- `0x180063fdc`

## string_xrefs

- `0x180064055`: `onecore\ds\security\cryptoapi\ncrypt\msprim\base\kem.c`

## pseudocode

```c
__int64 __fastcall GetCompositeMlKemBlobInfo(char *a1, wchar_t ***a2)
{
  wchar_t **v2; // r8
  __int64 i; // r9
  __int64 v6; // rcx
  wchar_t *v7; // rdx
  char *v8; // rax
  char *v9; // rdx
  int v10; // r11d
  int v11; // r10d
  unsigned int v12; // ebx

  v2 = 0;
  for ( i = 0; i != 3; ++i )
  {
    v6 = 0;
    do
    {
      v7 = (&(&off_180087130)[4 * i])[v6];
      if ( !v7 )
        break;
      v8 = a1;
      v9 = (char *)((char *)v7 - a1);
      do
      {
        v10 = *(unsigned __int16 *)&v9[(_QWORD)v8];
        v11 = *(unsigned __int16 *)v8 - v10;
        if ( v11 )
          break;
        v8 += 2;
      }
      while ( v10 );
      if ( !v11 )
      {
        v2 = &(&off_180087130)[4 * i];
        break;
      }
      v6 = (unsigned int)(v6 + 1);
    }
    while ( (unsigned int)v6 < 2 );
  }
  if ( v2 )
  {
    v12 = 0;
    *a2 = v2;
  }
  else
  {
    v12 = -1073741637;
    DebugTraceError(3221225659LL, "Status", "onecore\\ds\\security\\cryptoapi\\ncrypt\\msprim\\base\\kem.c", 585);
  }
  return v12;
}

```

## disassembly

```asm
0x180063fdc  mov     [rsp+arg_0], rbx
0x180063fe1  mov     [rsp+arg_8], rsi
0x180063fe6  push    rdi
0x180063fe7  sub     rsp, 20h
0x180063feb  xor     r8d, r8d
0x180063fee  mov     rdi, rdx
0x180063ff1  xor     r9d, r9d
0x180063ff4  mov     rsi, rcx
0x180063ff7  lea     rcx, off_180087130; "COMPMLKEMPRIVATEIRTFSEEDBLOB"
0x180063ffe  mov     rbx, r9
0x180064001  shl     rbx, 5
0x180064005  add     rbx, rcx
0x180064008  xor     ecx, ecx
0x18006400a  mov     rdx, [rbx+rcx*8]
0x18006400e  test    rdx, rdx
0x180064011  jz      short loc_180064041
0x180064013  mov     rax, rsi
0x180064016  sub     rdx, rsi
0x180064019  movzx   r10d, word ptr [rax]
0x18006401d  movzx   r11d, word ptr [rax+rdx]
0x180064022  sub     r10d, r11d
0x180064025  jnz     short loc_180064030
0x180064027  add     rax, 2
0x18006402b  test    r11d, r11d
0x18006402e  jnz     short loc_180064019
0x180064030  test    r10d, r10d
0x180064033  jz      short loc_18006403E
0x180064035  inc     ecx
0x180064037  cmp     ecx, 2
0x18006403a  jb      short loc_18006400A
0x18006403c  jmp     short loc_180064041
0x18006403e  mov     r8, rbx
0x180064041  inc     r9
0x180064044  cmp     r9, 3
0x180064048  jnz     short loc_180063FF7
0x18006404a  test    r8, r8
0x18006404d  jnz     short loc_180064074
0x18006404f  mov     r9d, 249h
0x180064055  lea     r8, aOnecoreDsSecur_27; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18006405c  lea     rdx, aStatus; "Status"
0x180064063  mov     ecx, 0C00000BBh
0x180064068  mov     ebx, 0C00000BBh
0x18006406d  call    DebugTraceError
0x180064072  jmp     short loc_180064079
0x180064074  xor     ebx, ebx
0x180064076  mov     [rdi], r8
0x180064079  mov     rsi, [rsp+28h+arg_8]
0x18006407e  mov     eax, ebx
0x180064080  mov     rbx, [rsp+28h+arg_0]
0x180064085  add     rsp, 20h
0x180064089  pop     rdi
0x18006408a  retn
```
