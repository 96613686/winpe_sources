# GetServerSddlString(APF_SERVER_SECURITY_ENUM,ushort *,int)

- ea: `0x180006ac4`
- end: `0x180006c8d`
- name: `?GetServerSddlString@@YAJW4APF_SERVER_SECURITY_ENUM@@PEAGH@Z`
- size: `457`
- prototype: `__int64 __fastcall(int, _WORD *)`
- caller_count: `1`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callers

- `0x180006c94`

## callees

- `0x180004924`
- `0x180006ac4`

## string_xrefs

- `0x180006c16`: `onecoreuap\drivers\wdm\audio\backpln\apx\service\core\apfsvc.cpp`

## pseudocode

```c
__int64 __fastcall GetServerSddlString(int a1, _WORD *a2)
{
  int v3; // ecx
  int v4; // ecx
  __int64 v5; // rax
  const wchar_t *v6; // rcx
  __int64 v7; // r8
  _WORD *v8; // rdx
  unsigned int v9; // ebx
  __int64 v10; // rdx
  __int64 v11; // rax
  const wchar_t *v12; // rcx
  __int64 v13; // r8
  _WORD *v14; // rdx
  __int64 v15; // rax
  const wchar_t *v16; // rcx
  __int64 v17; // r8
  _WORD *v18; // rdx
  __int64 v20; // rax
  const wchar_t *v21; // rcx
  __int64 v22; // r8
  _WORD *v23; // rdx
  int v24; // [rsp+20h] [rbp-8h]
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]

  if ( !a1 )
    goto LABEL_30;
  v3 = a1 - 1;
  if ( !v3 )
  {
    v15 = 2147483646;
    v16 = L"O:SYG:SYD:(A;;GRGWGX;;;WD)(A;;GRGWGX;;;RC)(A;;GA;;;BA)(A;;GA;;;OW)(A;;GR;;;AC)";
    v17 = 512;
    do
    {
      if ( !v15 )
        break;
      if ( !*v16 )
        break;
      *a2++ = *v16++;
      --v15;
      --v17;
    }
    while ( v17 );
    v18 = a2 - 1;
    v9 = v17 == 0 ? 0x8007007A : 0;
    if ( v17 )
      v18 = a2;
    *v18 = 0;
    if ( !v17 )
    {
      v10 = 384;
      goto LABEL_29;
    }
    return 0;
  }
  v4 = v3 - 1;
  if ( !v4 )
  {
LABEL_30:
    v20 = 2147483646;
    v21 = L"O:SYG:SYD:(A;;GA;;;BA)(A;;GA;;;OW)(A;;GA;;;S-1-15-3-787448254-1207972858-3558633622-1059886964)";
    v22 = 512;
    do
    {
      if ( !v20 )
        break;
      if ( !*v21 )
        break;
      *a2++ = *v21++;
      --v20;
      --v22;
    }
    while ( v22 );
    v23 = a2 - 1;
    v9 = v22 == 0 ? 0x8007007A : 0;
    if ( v22 )
      v23 = a2;
    *v23 = 0;
    if ( !v22 )
    {
      v10 = 447;
      goto LABEL_29;
    }
    return 0;
  }
  if ( v4 == 2 )
  {
    v5 = 2147483646;
    v6 = L"O:LSG:LSD:(A;;GRGWGX;;;WD)(A;;GRGWGX;;;RC)(A;;GA;;;BA)(A;;GA;;;OW)(A;;GR;;;AC)";
    v7 = 512;
    do
    {
      if ( !v5 )
        break;
      if ( !*v6 )
        break;
      *a2++ = *v6++;
      --v5;
      --v7;
    }
    while ( v7 );
    v8 = a2 - 1;
    v9 = v7 == 0 ? 0x8007007A : 0;
    if ( v7 )
      v8 = a2;
    *v8 = 0;
    if ( !v7 )
    {
      v10 = 400;
LABEL_29:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v10,
        (unsigned int)"onecoreuap\\drivers\\wdm\\audio\\backpln\\apx\\service\\core\\apfsvc.cpp",
        (const char *)v9,
        v24);
      return v9;
    }
  }
  else
  {
    v11 = 2147483646;
    v12 = L"O:LSG:LSD:(A;;GA;;;BA)(A;;GA;;;OW)(A;;GA;;;S-1-15-3-787448254-1207972858-3558633622-1059886964)";
    v13 = 512;
    do
    {
      if ( !v11 )
        break;
      if ( !*v12 )
        break;
      *a2++ = *v12++;
      --v11;
      --v13;
    }
    while ( v13 );
    v14 = a2 - 1;
    v9 = v13 == 0 ? 0x8007007A : 0;
    if ( v13 )
      v14 = a2;
    *v14 = 0;
    if ( !v13 )
    {
      v10 = 463;
      goto LABEL_29;
    }
  }
  return 0;
}

```

## disassembly

```asm
0x180006ac4  push    rbx; int
0x180006ac6  sub     rsp, 20h
0x180006aca  xor     r10d, r10d
0x180006acd  mov     r9, rdx
0x180006ad0  test    ecx, ecx
0x180006ad2  jz      loc_180006C29
0x180006ad8  sub     ecx, 1
0x180006adb  jz      loc_180006BB7
0x180006ae1  sub     ecx, 1
0x180006ae4  jz      loc_180006C29
0x180006aea  sub     ecx, 1
0x180006aed  jz      short loc_180006B57
0x180006aef  cmp     ecx, 1
0x180006af2  jnz     short loc_180006B57
0x180006af4  mov     eax, 7FFFFFFEh
0x180006af9  lea     rcx, aOLsgLsdAGrgwgx; "O:LSG:LSD:(A;;GRGWGX;;;WD)(A;;GRGWGX;;;"...
0x180006b00  mov     r8d, 200h
0x180006b06  test    rax, rax
0x180006b09  jz      short loc_180006B28
0x180006b0b  movzx   edx, word ptr [rcx]
0x180006b0e  test    dx, dx
0x180006b11  jz      short loc_180006B28
0x180006b13  mov     [r9], dx
0x180006b17  add     rcx, 2
0x180006b1b  add     r9, 2
0x180006b1f  dec     rax
0x180006b22  sub     r8, 1
0x180006b26  jnz     short loc_180006B06
0x180006b28  mov     rax, r8
0x180006b2b  lea     rdx, [r9-2]
0x180006b2f  neg     rax
0x180006b32  sbb     ebx, ebx
0x180006b34  not     ebx
0x180006b36  and     ebx, 8007007Ah
0x180006b3c  test    r8, r8
0x180006b3f  cmovnz  rdx, r9
0x180006b43  mov     [rdx], r10w
0x180006b47  jnz     loc_180006C85
0x180006b4d  mov     edx, 190h
0x180006b52  jmp     loc_180006C11
0x180006b57  mov     eax, 7FFFFFFEh
0x180006b5c  lea     rcx, aOLsgLsdAGaBaAG; "O:LSG:LSD:(A;;GA;;;BA)(A;;GA;;;OW)(A;;G"...
0x180006b63  mov     r8d, 200h
0x180006b69  test    rax, rax
0x180006b6c  jz      short loc_180006B8B
0x180006b6e  movzx   edx, word ptr [rcx]
0x180006b71  test    dx, dx
0x180006b74  jz      short loc_180006B8B
0x180006b76  mov     [r9], dx
0x180006b7a  add     rcx, 2
0x180006b7e  add     r9, 2
0x180006b82  dec     rax
0x180006b85  sub     r8, 1
0x180006b89  jnz     short loc_180006B69
0x180006b8b  mov     rax, r8
0x180006b8e  lea     rdx, [r9-2]
0x180006b92  neg     rax
0x180006b95  sbb     ebx, ebx
0x180006b97  not     ebx
0x180006b99  and     ebx, 8007007Ah
0x180006b9f  test    r8, r8
0x180006ba2  cmovnz  rdx, r9
0x180006ba6  mov     [rdx], r10w
0x180006baa  jnz     loc_180006C85
0x180006bb0  mov     edx, 1CFh
0x180006bb5  jmp     short loc_180006C11
0x180006bb7  mov     eax, 7FFFFFFEh
0x180006bbc  lea     rcx, aOSygSydAGrgwgx; "O:SYG:SYD:(A;;GRGWGX;;;WD)(A;;GRGWGX;;;"...
0x180006bc3  mov     r8d, 200h
0x180006bc9  test    rax, rax
0x180006bcc  jz      short loc_180006BEB
0x180006bce  movzx   edx, word ptr [rcx]
0x180006bd1  test    dx, dx
0x180006bd4  jz      short loc_180006BEB
0x180006bd6  mov     [r9], dx
0x180006bda  add     rcx, 2
0x180006bde  add     r9, 2
0x180006be2  dec     rax
0x180006be5  sub     r8, 1
0x180006be9  jnz     short loc_180006BC9
0x180006beb  mov     rax, r8
0x180006bee  lea     rdx, [r9-2]
0x180006bf2  neg     rax
0x180006bf5  sbb     ebx, ebx
0x180006bf7  not     ebx
0x180006bf9  and     ebx, 8007007Ah
0x180006bff  test    r8, r8
0x180006c02  cmovnz  rdx, r9
0x180006c06  mov     [rdx], r10w
0x180006c0a  jnz     short loc_180006C85
0x180006c0c  mov     edx, 180h; void *
0x180006c11  mov     rcx, [rsp+28h]; this
0x180006c16  lea     r8, aOnecoreuapDriv; "onecoreuap\\drivers\\wdm\\audio\\backpl"...
0x180006c1d  mov     r9d, ebx; char *
0x180006c20  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180006c25  mov     eax, ebx
0x180006c27  jmp     short loc_180006C87
0x180006c29  mov     eax, 7FFFFFFEh
0x180006c2e  lea     rcx, aOSygSydAGaBaAG; "O:SYG:SYD:(A;;GA;;;BA)(A;;GA;;;OW)(A;;G"...
0x180006c35  mov     r8d, 200h
0x180006c3b  test    rax, rax
0x180006c3e  jz      short loc_180006C5D
0x180006c40  movzx   edx, word ptr [rcx]
0x180006c43  test    dx, dx
0x180006c46  jz      short loc_180006C5D
0x180006c48  mov     [r9], dx
0x180006c4c  add     rcx, 2
0x180006c50  add     r9, 2
0x180006c54  dec     rax
0x180006c57  sub     r8, 1
0x180006c5b  jnz     short loc_180006C3B
0x180006c5d  mov     rax, r8
0x180006c60  lea     rdx, [r9-2]
0x180006c64  neg     rax
0x180006c67  sbb     ebx, ebx
0x180006c69  not     ebx
0x180006c6b  and     ebx, 8007007Ah
0x180006c71  test    r8, r8
0x180006c74  cmovnz  rdx, r9
0x180006c78  mov     [rdx], r10w
0x180006c7c  jnz     short loc_180006C85
0x180006c7e  mov     edx, 1BFh
0x180006c83  jmp     short loc_180006C11
0x180006c85  xor     eax, eax
0x180006c87  add     rsp, 20h
0x180006c8b  pop     rbx
0x180006c8c  retn
```
