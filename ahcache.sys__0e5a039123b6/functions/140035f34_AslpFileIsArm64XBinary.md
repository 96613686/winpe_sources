# AslpFileIsArm64XBinary

- ea: `0x140035f34`
- end: `0x1400360e1`
- name: `AslpFileIsArm64XBinary`
- size: `429`
- prototype: `__int64 __fastcall(bool *, __int64)`
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, service_task`

## callers

- `0x14004a724`

## callees

- `0x1400079b6`
- `0x1400345a4`
- `0x140035f34`
- `0x140036568`
- `0x14003e364`
- `0x140051e8c`

## string_xrefs

- `0x140036005`: `AslpFileGetImageNtHeader failed [%x]`
- `0x140036079`: `AslpImageRvaToVa failed to find LoadConfigTableDirectory RVA`

## pseudocode

```c
__int64 __fastcall AslpFileIsArm64XBinary(bool *a1, __int64 a2)
{
  unsigned int v4; // ebx
  int FileKindDetail; // eax
  const char *v6; // r9
  __int64 v7; // r8
  __int64 v8; // rbx
  __int64 v9; // rsi
  unsigned __int64 v10; // r15
  __int64 v11; // r12
  __int64 v12; // rax
  unsigned int v14; // [rsp+60h] [rbp+8h] BYREF
  __int64 v15; // [rsp+70h] [rbp+18h] BYREF

  v14 = 0;
  v15 = 0;
  v4 = -1073741584;
  if ( a1 )
  {
    *a1 = 0;
    FileKindDetail = AslFileMappingGetFileKindDetail(&v14);
    v4 = FileKindDetail;
    if ( FileKindDetail < 0 )
    {
      v6 = "AslFileMappingGetFileKindDetails failed [%x]";
      v7 = 5858;
LABEL_4:
      AslLogCallPrintf(1, "AslpFileIsArm64XBinary", v7, v6, FileKindDetail);
      return v4;
    }
    if ( v14 <= 4 )
      return (unsigned int)-2147483614;
    if ( v14 == 8 || v14 == 9 || v14 == 10 || v14 == 15 )
    {
      FileKindDetail = AslpFileGetImageNtHeader(&v15, a2);
      v4 = FileKindDetail;
      if ( FileKindDetail < 0 )
      {
        v6 = "AslpFileGetImageNtHeader failed [%x]";
        v7 = 5890;
        goto LABEL_4;
      }
      v8 = v15;
      if ( *(_DWORD *)(v15 + 216) )
      {
        v9 = 0;
        v10 = *(unsigned __int16 *)(v15 + 6);
        v11 = v15 + *(unsigned __int16 *)(v15 + 20) + 24LL;
        if ( *(_WORD *)(v15 + 6) )
        {
          while ( strncmp_0(".a64xrm", (const char *)(v11 + 40 * v9), 8u) )
          {
            if ( ++v9 >= v10 )
              goto LABEL_17;
          }
          *a1 = 1;
        }
        else
        {
LABEL_17:
          v12 = AslpImageRvaToVa(v8, a2);
          if ( !v12 )
          {
            v4 = -1073741275;
            AslLogCallPrintf(
              1,
              "AslpFileIsArm64XBinary",
              5921,
              "AslpImageRvaToVa failed to find LoadConfigTableDirectory RVA");
            return v4;
          }
          if ( *(_DWORD *)v12 >= 0xD0u )
            *a1 = *(_QWORD *)(v12 + 200) != 0;
        }
      }
    }
    return 0;
  }
  return v4;
}

```

## disassembly

```asm
0x140035f34  mov     rax, rsp
0x140035f37  mov     [rax+10h], rbx
0x140035f3b  mov     [rax+20h], rbp
0x140035f3f  push    rsi
0x140035f40  push    rdi
0x140035f41  push    r12
0x140035f43  push    r14
0x140035f45  push    r15
0x140035f47  sub     rsp, 30h
0x140035f4b  mov     dword ptr [rax+8], 0
0x140035f52  mov     rbp, rdx
0x140035f55  mov     qword ptr [rax+18h], 0
0x140035f5d  mov     rdi, rcx
0x140035f60  mov     ebx, 0C00000F0h
0x140035f65  test    rcx, rcx
0x140035f68  jz      loc_1400360C7
0x140035f6e  mov     byte ptr [rcx], 0
0x140035f71  lea     rcx, [rax+8]
0x140035f75  call    AslFileMappingGetFileKindDetail
0x140035f7a  mov     ebx, eax
0x140035f7c  test    eax, eax
0x140035f7e  jns     short loc_140035FA7
0x140035f80  lea     r9, aAslfilemapping; "AslFileMappingGetFileKindDetails failed"...
0x140035f87  mov     r8d, 16E2h
0x140035f8d  lea     rdx, aAslpfileisarm6; "AslpFileIsArm64XBinary"
0x140035f94  mov     [rsp+58h+var_38], eax
0x140035f98  mov     ecx, 1
0x140035f9d  call    AslLogCallPrintf
0x140035fa2  jmp     loc_1400360C7
0x140035fa7  mov     ecx, [rsp+58h+arg_0]
0x140035fab  test    ecx, ecx
0x140035fad  jz      loc_1400360C2
0x140035fb3  sub     ecx, 1
0x140035fb6  jz      loc_1400360C2
0x140035fbc  sub     ecx, 1
0x140035fbf  jz      loc_1400360C2
0x140035fc5  sub     ecx, 1
0x140035fc8  jz      loc_1400360C2
0x140035fce  sub     ecx, 1
0x140035fd1  jz      loc_1400360C2
0x140035fd7  sub     ecx, 4
0x140035fda  jz      short loc_140035FF2
0x140035fdc  sub     ecx, 1
0x140035fdf  jz      short loc_140035FF2
0x140035fe1  sub     ecx, 1
0x140035fe4  jz      short loc_140035FF2
0x140035fe6  cmp     ecx, 5
0x140035fe9  jz      short loc_140035FF2
0x140035feb  xor     ebx, ebx
0x140035fed  jmp     loc_1400360C7
0x140035ff2  mov     rdx, rbp
0x140035ff5  lea     rcx, [rsp+58h+arg_10]
0x140035ffa  call    AslpFileGetImageNtHeader
0x140035fff  mov     ebx, eax
0x140036001  test    eax, eax
0x140036003  jns     short loc_140036017
0x140036005  lea     r9, aAslpfilegetima_1; "AslpFileGetImageNtHeader failed [%x]"
0x14003600c  mov     r8d, 1702h
0x140036012  jmp     loc_140035F8D
0x140036017  mov     rbx, [rsp+58h+arg_10]
0x14003601c  mov     r14d, [rbx+0D8h]
0x140036023  test    r14d, r14d
0x140036026  jz      short loc_140035FEB
0x140036028  movzx   r12d, word ptr [rbx+14h]
0x14003602d  xor     esi, esi
0x14003602f  movzx   r15d, word ptr [rbx+6]
0x140036034  add     r12, 18h
0x140036038  add     r12, rbx
0x14003603b  test    r15, r15
0x14003603e  jz      short loc_140036066
0x140036040  lea     rax, [rsi+rsi*4]
0x140036044  mov     r8d, 8; MaxCount
0x14003604a  lea     rdx, [r12+rax*8]; Str2
0x14003604e  lea     rcx, aA64xrm; ".a64xrm"
0x140036055  call    strncmp_0
0x14003605a  test    eax, eax
0x14003605c  jz      short loc_14003609C
0x14003605e  inc     rsi
0x140036061  cmp     rsi, r15
0x140036064  jb      short loc_140036040
0x140036066  mov     r8d, r14d
0x140036069  mov     rdx, rbp
0x14003606c  mov     rcx, rbx
0x14003606f  call    AslpImageRvaToVa
0x140036074  test    rax, rax
0x140036077  jnz     short loc_1400360A4
0x140036079  lea     r9, aAslpimagervato; "AslpImageRvaToVa failed to find LoadCon"...
0x140036080  mov     r8d, 1721h
0x140036086  lea     rdx, aAslpfileisarm6; "AslpFileIsArm64XBinary"
0x14003608d  mov     ebx, 0C0000225h
0x140036092  lea     ecx, [rax+1]
0x140036095  call    AslLogCallPrintf
0x14003609a  jmp     short loc_1400360C7
0x14003609c  mov     byte ptr [rdi], 1
0x14003609f  jmp     loc_140035FEB
0x1400360a4  cmp     dword ptr [rax], 0D0h
0x1400360aa  jb      loc_140035FEB
0x1400360b0  cmp     qword ptr [rax+0C8h], 0
0x1400360b8  setnz   al
0x1400360bb  mov     [rdi], al
0x1400360bd  jmp     loc_140035FEB
0x1400360c2  mov     ebx, 80000022h
0x1400360c7  mov     rbp, [rsp+58h+arg_18]
0x1400360cc  mov     eax, ebx
0x1400360ce  mov     rbx, [rsp+58h+arg_8]
0x1400360d3  add     rsp, 30h
0x1400360d7  pop     r15
0x1400360d9  pop     r14
0x1400360db  pop     r12
0x1400360dd  pop     rdi
0x1400360de  pop     rsi
0x1400360df  retn
```
