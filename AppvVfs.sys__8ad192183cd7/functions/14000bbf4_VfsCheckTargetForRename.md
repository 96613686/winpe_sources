# VfsCheckTargetForRename

- ea: `0x14000bbf4`
- end: `0x14000bdc5`
- name: `VfsCheckTargetForRename`
- size: `465`
- prototype: `__int64 __fastcall(__int64, struct _FLT_INSTANCE *, __int64, __int64, PFLT_INSTANCE Instance, __int64, __int64, __int64, __int64, __int64, unsigned int *)`
- caller_count: `2`
- callee_count: `4`
- tags: `loader_planting`

## callers

- `0x14000b4ec`
- `0x14000bdcc`

## callees

- `0x1400031bc`
- `0x140007bac`
- `0x14000b2dc`
- `0x14000bbf4`

## pseudocode

```c
__int64 __fastcall VfsCheckTargetForRename(
        __int64 a1,
        struct _FLT_INSTANCE *a2,
        __int64 a3,
        __int64 a4,
        PFLT_INSTANCE Instance,
        __int64 a6,
        __int64 a7,
        __int64 a8,
        __int64 a9,
        __int64 a10,
        unsigned int *a11)
{
  __int64 v11; // rax
  char *v15; // rsi
  __int64 result; // rax
  __int64 v18; // rdi
  unsigned int v19; // ebx
  __int16 v20; // dx
  __int64 v21; // r9
  unsigned __int16 i; // r8
  __int16 v23; // cx
  __int64 v24; // rcx
  char v25; // al
  UNICODE_STRING SourceString; // [rsp+50h] [rbp-58h] BYREF
  __int64 v27; // [rsp+B0h] [rbp+8h] BYREF

  v11 = *(_QWORD *)(a1 + 16);
  LODWORD(v27) = 0;
  v15 = *(char **)(v11 + 56);
  SourceString = 0;
  if ( !a2 && !Instance )
    return 3221225485LL;
  v18 = a7;
  result = VfsCowQueryFile((int)a2, a3, a4, 0, 0, Instance, a6, a7, (__int64)&v27);
  if ( (int)result >= 0 )
  {
    v19 = v27;
    if ( (v27 & 0x400) != 0 )
    {
      return 3221225506LL;
    }
    else
    {
      v20 = *(_WORD *)v18 >> 1;
      if ( v20 )
      {
        v21 = *(_QWORD *)(v18 + 8);
        for ( i = v20 - 1; ; --i )
        {
          v23 = *(_WORD *)(v21 + 2LL * i);
          if ( v23 == 92 )
            break;
          if ( v23 == 58 )
          {
            v20 = i + 1;
          }
          else if ( v23 == 46 )
          {
            SourceString.MaximumLength = 2 * (v20 - i) - 2;
            SourceString.Length = SourceString.MaximumLength;
            SourceString.Buffer = (wchar_t *)(v21 + 2 + 2LL * i);
            if ( (unsigned __int8)VfsIsExcludedExtension(&SourceString) )
              return 3221225506LL;
            break;
          }
          if ( !i )
            break;
        }
      }
      v24 = (v19 >> 6) & 1;
      if ( ((v19 >> 6) & 1) == 0 && (v19 & 0x80u) == 0 || (v19 & 0x200) != 0 )
        goto LABEL_27;
      if ( *(_DWORD *)(*(_QWORD *)(a1 + 16) + 32LL) == 10 )
        v25 = *v15;
      else
        v25 = *(_DWORD *)v15 & 1;
      if ( !v25 )
        return 3221225525LL;
      if ( !(_DWORD)v24
        || (v19 & 0x80u) != 0
        || (result = VfsCheckPackageFileForDelete(v24, a2, a3, a4, a8, a9, a10), (int)result >= 0) )
      {
LABEL_27:
        *a11 = v19;
        return 0;
      }
    }
  }
  return result;
}

```

## disassembly

```asm
0x14000bbf4  mov     r11, rsp
0x14000bbf7  push    rbx
0x14000bbf8  push    rbp
0x14000bbf9  push    rsi
0x14000bbfa  push    rdi
0x14000bbfb  push    r12
0x14000bbfd  push    r13
0x14000bbff  push    r14
0x14000bc01  push    r15
0x14000bc03  sub     rsp, 68h
0x14000bc07  mov     rax, [rcx+10h]
0x14000bc0b  xor     r13d, r13d
0x14000bc0e  mov     r10, [rsp+0A8h+arg_20]
0x14000bc16  xorps   xmm0, xmm0
0x14000bc19  mov     [r11+8], r13d
0x14000bc1d  mov     r15, r9
0x14000bc20  mov     r12, r8
0x14000bc23  mov     rbp, rdx
0x14000bc26  mov     rsi, [rax+38h]
0x14000bc2a  mov     r14, rcx
0x14000bc2d  movups  xmmword ptr [rsp+0A8h+SourceString.Length], xmm0
0x14000bc32  test    rdx, rdx
0x14000bc35  jnz     short loc_14000BC46
0x14000bc37  test    r10, r10
0x14000bc3a  jnz     short loc_14000BC46
0x14000bc3c  mov     eax, 0C000000Dh
0x14000bc41  jmp     loc_14000BDB3
0x14000bc46  mov     rdi, [rsp+0A8h+arg_30]
0x14000bc4e  lea     rax, [rsp+0A8h+arg_0]
0x14000bc56  mov     [rsp+0A8h+var_68], rax; __int64
0x14000bc5b  xor     r9d, r9d; int
0x14000bc5e  mov     rax, [rsp+0A8h+arg_28]
0x14000bc66  mov     r8, r15; int
0x14000bc69  mov     [rsp+0A8h+var_70], rdi; __int64
0x14000bc6e  mov     rdx, r12; int
0x14000bc71  mov     [rsp+0A8h+var_78], rax; __int64
0x14000bc76  mov     rcx, rbp; int
0x14000bc79  mov     [rsp+0A8h+Instance], r10; Instance
0x14000bc7e  mov     [rsp+0A8h+var_88], r13; __int64
0x14000bc83  call    VfsCowQueryFile
0x14000bc88  test    eax, eax
0x14000bc8a  js      loc_14000BDB3
0x14000bc90  mov     ebx, dword ptr [rsp+0A8h+arg_0]
0x14000bc97  bt      ebx, 0Ah
0x14000bc9b  jb      loc_14000BDAE
0x14000bca1  movzx   edx, word ptr [rdi]
0x14000bca4  mov     r10d, 1
0x14000bcaa  shr     dx, 1
0x14000bcad  jz      short loc_14000BD2D
0x14000bcaf  mov     r9, [rdi+8]
0x14000bcb3  movzx   r8d, dx
0x14000bcb7  sub     r8w, r10w
0x14000bcbb  jmp     short loc_14000BCDE
0x14000bcbd  cmp     cx, 3Ah ; ':'
0x14000bcc1  jnz     short loc_14000BCC9
0x14000bcc3  lea     edx, [r10+r8]
0x14000bcc7  jmp     short loc_14000BCCF
0x14000bcc9  cmp     cx, 2Eh ; '.'
0x14000bccd  jz      short loc_14000BCEF
0x14000bccf  test    r8w, r8w
0x14000bcd3  jz      short loc_14000BD2D
0x14000bcd5  mov     eax, 0FFFFh
0x14000bcda  add     r8w, ax
0x14000bcde  movzx   eax, r8w
0x14000bce2  movzx   ecx, word ptr [r9+rax*2]
0x14000bce7  cmp     cx, 5Ch ; '\'
0x14000bceb  jnz     short loc_14000BCBD
0x14000bced  jmp     short loc_14000BD2D
0x14000bcef  sub     dx, r8w
0x14000bcf3  movzx   eax, r8w
0x14000bcf7  add     r9, 2
0x14000bcfb  add     dx, dx
0x14000bcfe  sub     dx, 2
0x14000bd02  mov     [rsp+0A8h+SourceString.MaximumLength], dx
0x14000bd07  mov     [rsp+0A8h+SourceString.Length], dx
0x14000bd0c  lea     rcx, [r9+rax*2]
0x14000bd10  mov     [rsp+0A8h+SourceString.Buffer], rcx
0x14000bd15  lea     rcx, [rsp+0A8h+SourceString]; SourceString
0x14000bd1a  call    VfsIsExcludedExtension
0x14000bd1f  test    al, al
0x14000bd21  jnz     loc_14000BDAE
0x14000bd27  mov     r10d, 1
0x14000bd2d  mov     ecx, ebx
0x14000bd2f  shr     ecx, 6
0x14000bd32  and     ecx, r10d
0x14000bd35  jnz     short loc_14000BD3B
0x14000bd37  test    bl, bl
0x14000bd39  jns     short loc_14000BDA0
0x14000bd3b  bt      ebx, 9
0x14000bd3f  jb      short loc_14000BDA0
0x14000bd41  mov     rax, [r14+10h]
0x14000bd45  cmp     dword ptr [rax+20h], 0Ah
0x14000bd49  jnz     short loc_14000BD4F
0x14000bd4b  mov     al, [rsi]
0x14000bd4d  jmp     short loc_14000BD54
0x14000bd4f  mov     eax, [rsi]
0x14000bd51  and     al, r10b
0x14000bd54  test    al, al
0x14000bd56  jnz     short loc_14000BD5F
0x14000bd58  mov     eax, 0C0000035h
0x14000bd5d  jmp     short loc_14000BDB3
0x14000bd5f  test    ecx, ecx
0x14000bd61  jz      short loc_14000BDA0
0x14000bd63  test    bl, bl
0x14000bd65  js      short loc_14000BDA0
0x14000bd67  mov     rax, [rsp+0A8h+arg_48]
0x14000bd6f  mov     r9, r15
0x14000bd72  mov     [rsp+0A8h+var_78], rax
0x14000bd77  mov     r8, r12
0x14000bd7a  mov     rax, [rsp+0A8h+arg_40]
0x14000bd82  mov     rdx, rbp
0x14000bd85  mov     [rsp+0A8h+Instance], rax
0x14000bd8a  mov     rax, [rsp+0A8h+arg_38]
0x14000bd92  mov     [rsp+0A8h+var_88], rax
0x14000bd97  call    VfsCheckPackageFileForDelete
0x14000bd9c  test    eax, eax
0x14000bd9e  js      short loc_14000BDB3
0x14000bda0  mov     rax, [rsp+0A8h+arg_50]
0x14000bda8  mov     [rax], ebx
0x14000bdaa  xor     eax, eax
0x14000bdac  jmp     short loc_14000BDB3
0x14000bdae  mov     eax, 0C0000022h
0x14000bdb3  add     rsp, 68h
0x14000bdb7  pop     r15
0x14000bdb9  pop     r14
0x14000bdbb  pop     r13
0x14000bdbd  pop     r12
0x14000bdbf  pop     rdi
0x14000bdc0  pop     rsi
0x14000bdc1  pop     rbp
0x14000bdc2  pop     rbx
0x14000bdc3  retn
```
