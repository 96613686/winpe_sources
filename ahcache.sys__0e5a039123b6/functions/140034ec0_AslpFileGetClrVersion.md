# AslpFileGetClrVersion

- ea: `0x140034ec0`
- end: `0x140035064`
- name: `AslpFileGetClrVersion`
- size: `420`
- prototype: `__int64 __fastcall(_BYTE *, __int64)`
- caller_count: `1`
- callee_count: `5`
- tags: `service_task, broker_com_uri`

## callers

- `0x14003506c`

## callees

- `0x140007b40`
- `0x140034ec0`
- `0x140036568`
- `0x14003e364`
- `0x140051e8c`

## string_xrefs

- `0x140034ef2`: `AslpFileGetImageNtHeader failed [%x]`
- `0x140034f6f`: `Invalid COM Descriptor virtual address encountered`

## pseudocode

```c
__int64 __fastcall AslpFileGetClrVersion(_BYTE *a1, __int64 a2)
{
  _DWORD *v4; // rdi
  int ImageNtHeader; // eax
  unsigned int v6; // ebx
  __int64 v7; // rbx
  __int16 v8; // ax
  __int64 v9; // rax
  const char *v10; // r9
  __int64 v11; // r8
  _DWORD *v12; // rax
  __int64 v13; // rbx
  __int64 v15; // [rsp+70h] [rbp+8h] BYREF

  v15 = 0;
  v4 = 0;
  *a1 = 0;
  ImageNtHeader = AslpFileGetImageNtHeader(&v15, a2);
  v6 = ImageNtHeader;
  if ( ImageNtHeader >= 0 )
  {
    v7 = v15;
    v8 = *(_WORD *)(v15 + 24);
    if ( v8 == 267 )
    {
      v4 = (_DWORD *)(v15 + 232);
    }
    else if ( v8 == 523 )
    {
      v4 = (_DWORD *)(v15 + 248);
    }
    if ( !v4 || !*v4 || v4[1] < 0x48u )
      return (unsigned int)-1073741701;
    v9 = AslpImageRvaToVa(v15, a2);
    if ( v9 )
    {
      if ( *(_WORD *)(v9 + 4) != 2 )
        return (unsigned int)-1073741637;
      v12 = (_DWORD *)AslpImageRvaToVa(v7, a2);
      if ( v12 )
      {
        if ( *v12 != 1112167234 )
        {
          v6 = -1073741637;
          v10 = "Invalid COR20 Metadata signature encountered";
          v11 = 5739;
          goto LABEL_13;
        }
        v13 = (unsigned int)v12[3];
        if ( (unsigned __int64)(v13 - 1) <= 0xFE )
        {
          memmove(a1, v12 + 4, (unsigned int)v13);
          a1[v13] = 0;
          return 0;
        }
        v10 = "CLR version string null or too long";
        v11 = 5751;
      }
      else
      {
        v10 = "Invalid COR20 Metadata virtual address encountered";
        v11 = 5729;
      }
    }
    else
    {
      v10 = "Invalid COM Descriptor virtual address encountered";
      v11 = 5709;
    }
    v6 = -1073741701;
LABEL_13:
    AslLogCallPrintf(1, "AslpFileGetClrVersion", v11, v10);
    return v6;
  }
  AslLogCallPrintf(1, "AslpFileGetClrVersion", 5680, "AslpFileGetImageNtHeader failed [%x]", ImageNtHeader);
  return v6;
}

```

## disassembly

```asm
0x140034ec0  push    rbx
0x140034ec2  push    rsi
0x140034ec3  push    rdi
0x140034ec4  push    r14
0x140034ec6  sub     rsp, 48h
0x140034eca  mov     r14, rdx
0x140034ecd  mov     rsi, rcx
0x140034ed0  mov     [rsp+68h+arg_0], 0
0x140034ed9  xor     edi, edi
0x140034edb  mov     [rcx], dil
0x140034ede  lea     rcx, [rsp+68h+arg_0]
0x140034ee3  call    AslpFileGetImageNtHeader
0x140034ee8  mov     ebx, eax
0x140034eea  test    eax, eax
0x140034eec  jns     short loc_140034F13
0x140034eee  mov     [rsp+68h+var_48], eax
0x140034ef2  lea     r9, aAslpfilegetima_1; "AslpFileGetImageNtHeader failed [%x]"
0x140034ef9  mov     r8d, 1630h
0x140034eff  lea     rdx, aAslpfilegetclr; "AslpFileGetClrVersion"
0x140034f06  lea     ecx, [rdi+1]
0x140034f09  call    AslLogCallPrintf
0x140034f0e  jmp     loc_140035057
0x140034f13  mov     rbx, [rsp+68h+arg_0]
0x140034f18  movzx   eax, word ptr [rbx+18h]
0x140034f1c  mov     ecx, 10Bh
0x140034f21  cmp     ax, cx
0x140034f24  jnz     short loc_140034F2F
0x140034f26  lea     rdi, [rbx+0E8h]
0x140034f2d  jmp     short loc_140034F40
0x140034f2f  mov     ecx, 20Bh
0x140034f34  cmp     ax, cx
0x140034f37  jnz     short loc_140034F40
0x140034f39  lea     rdi, [rbx+0F8h]
0x140034f40  test    rdi, rdi
0x140034f43  jz      loc_140035023
0x140034f49  mov     r8d, [rdi]
0x140034f4c  test    r8d, r8d
0x140034f4f  jz      loc_140035023
0x140034f55  cmp     dword ptr [rdi+4], 48h ; 'H'
0x140034f59  jb      loc_140035023
0x140034f5f  mov     rdx, r14
0x140034f62  mov     rcx, rbx
0x140034f65  call    AslpImageRvaToVa
0x140034f6a  test    rax, rax
0x140034f6d  jnz     short loc_140034F9B
0x140034f6f  lea     r9, aInvalidComDesc; "Invalid COM Descriptor virtual address "...
0x140034f76  mov     r8d, 164Dh
0x140034f7c  mov     ebx, 0C000007Bh
0x140034f81  mov     [rsp+68h+var_38], ebx
0x140034f85  lea     rdx, aAslpfilegetclr; "AslpFileGetClrVersion"
0x140034f8c  mov     ecx, 1
0x140034f91  call    AslLogCallPrintf
0x140034f96  jmp     loc_14003502C
0x140034f9b  cmp     word ptr [rax+4], 2
0x140034fa0  jz      short loc_140034FA9
0x140034fa2  mov     ebx, 0C00000BBh
0x140034fa7  jmp     short loc_140035028
0x140034fa9  mov     r8d, [rax+8]
0x140034fad  mov     rdx, r14
0x140034fb0  mov     rcx, rbx
0x140034fb3  call    AslpImageRvaToVa
0x140034fb8  mov     rdx, rax
0x140034fbb  test    rax, rax
0x140034fbe  jnz     short loc_140034FCF
0x140034fc0  lea     r9, aInvalidCor20Me; "Invalid COR20 Metadata virtual address "...
0x140034fc7  mov     r8d, 1661h
0x140034fcd  jmp     short loc_140034F7C
0x140034fcf  cmp     dword ptr [rax], 424A5342h
0x140034fd5  jz      short loc_140034FEB
0x140034fd7  mov     ebx, 0C00000BBh
0x140034fdc  lea     r9, aInvalidCor20Me_0; "Invalid COR20 Metadata signature encoun"...
0x140034fe3  mov     r8d, 166Bh
0x140034fe9  jmp     short loc_140034F81
0x140034feb  mov     ebx, [rax+0Ch]
0x140034fee  lea     rax, [rbx-1]
0x140034ff2  cmp     rax, 0FEh
0x140034ff8  ja      short loc_140035011
0x140034ffa  add     rdx, 10h; Src
0x140034ffe  mov     r8d, ebx; Size
0x140035001  mov     rcx, rsi; void *
0x140035004  call    memmove
0x140035009  mov     byte ptr [rbx+rsi], 0
0x14003500d  xor     ebx, ebx
0x14003500f  jmp     short loc_140035028
0x140035011  lea     r9, aClrVersionStri; "CLR version string null or too long"
0x140035018  mov     r8d, 1677h
0x14003501e  jmp     loc_140034F7C
0x140035023  mov     ebx, 0C000007Bh
0x140035028  mov     [rsp+68h+var_38], ebx
0x14003502c  jmp     short loc_140035057
0x14003502e  mov     ebx, eax
0x140035030  mov     [rsp+68h+var_38], eax
0x140035034  mov     [rsp+68h+var_48], eax
0x140035038  lea     r9, aExceptionEncou_0; "Exception encountered [%x]"
0x14003503f  mov     r8d, 168Eh
0x140035045  lea     rdx, aAslpfilegetclr; "AslpFileGetClrVersion"
0x14003504c  mov     ecx, 1
0x140035051  call    AslLogCallPrintf
0x140035056  nop
0x140035057  mov     eax, ebx
0x140035059  add     rsp, 48h
0x14003505d  pop     r14
0x14003505f  pop     rdi
0x140035060  pop     rsi
0x140035061  pop     rbx
0x140035062  retn
0x14005bf6b  push    rbp
0x14005bf6d  sub     rsp, 30h
0x14005bf71  mov     rbp, rdx
0x14005bf74  mov     eax, 1
0x14005bf79  add     rsp, 30h
0x14005bf7d  pop     rbp
0x14005bf7e  retn
```
