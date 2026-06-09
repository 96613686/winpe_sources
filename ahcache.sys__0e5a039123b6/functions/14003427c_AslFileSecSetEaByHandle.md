# AslFileSecSetEaByHandle

- ea: `0x14003427c`
- end: `0x14003440f`
- name: `AslFileSecSetEaByHandle`
- size: `403`
- prototype: `__int64 __fastcall(void *, _OWORD *, __int64, char *)`
- caller_count: `2`
- callee_count: `4`
- tags: ``

## callers

- `0x14002e034`
- `0x140034418`

## callees

- `0x14003427c`
- `0x14003e364`
- `0x140045d44`
- `0x14005498c`

## import_xrefs

- `ntoskrnl!ObReferenceObjectByHandle` at `0x14003435f`
- `ntoskrnl!ObReferenceObjectByHandle` at `0x14003435f`
- `ntoskrnl!IoFileObjectType` at `0x140034333`
- `ntoskrnl!_strnicmp` at `0x14003431c`
- `ntoskrnl!_strnicmp` at `0x14003431c`
- `ntoskrnl!FsRtlSetKernelEaFile` at `0x1400343a1`
- `ntoskrnl!FsRtlSetKernelEaFile` at `0x1400343a1`
- `ntoskrnl!ZwSetEaFile` at `0x1400343d0`
- `ntoskrnl!ZwSetEaFile` at `0x1400343d0`

## string_xrefs

- `0x1400342ed`: `$KERNEL.PURGE.AHC_READ_TIME`
- `0x1400342f4`: `$KERNEL.PURGE.AHC_READ_TIME`

## pseudocode

```c
__int64 __fastcall AslFileSecSetEaByHandle(void *a1, _OWORD *a2, __int64 a3, char *a4)
{
  __int64 v7; // rax
  void *v8; // rdi
  unsigned int v9; // ebx
  NTSTATUS v10; // eax
  const char *v11; // r9
  __int64 v12; // r8
  __int64 v13; // rcx
  PVOID *Object; // [rsp+20h] [rbp-48h]
  struct _IO_STATUS_BLOCK IoStatusBlock; // [rsp+30h] [rbp-38h] BYREF
  PVOID v16; // [rsp+70h] [rbp+8h] BYREF

  v16 = a1;
  if ( !a2 )
    return 3221225712LL;
  if ( (unsigned __int64)(a4 - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
  {
    IoStatusBlock = 0;
    v7 = AslAlloc(a1, 55, 1);
    v8 = (void *)v7;
    if ( !v7 )
      return (unsigned int)-1073741801;
    *(_DWORD *)v7 = 0;
    *(_DWORD *)(v7 + 4) = 1055488;
    strcpy((char *)(v7 + 8), "$KERNEL.PURGE.AHC_READ_TIME");
    *(_OWORD *)(v7 + 36) = *a2;
    if ( !_strnicmp("$KERNEL.PURGE.AHC_READ_TIME", "$KERNEL.", 8u) )
    {
      v16 = 0;
      v10 = ObReferenceObjectByHandle(a4, 1u, (POBJECT_TYPE)IoFileObjectType, 0, &v16, 0);
      v9 = v10;
      if ( v10 < 0 )
      {
        v11 = "ObReferenceObjectByHandle failed 0x%08lx\n";
        v12 = 639;
LABEL_9:
        LODWORD(Object) = v10;
        AslLogCallPrintf(1, "AslFileSecSetEaByHandle", v12, v11, Object);
LABEL_15:
        AslFree(v13, v8);
        return v9;
      }
      v10 = FsRtlSetKernelEaFile(v16, v8, 55);
      v9 = v10;
      if ( v10 < 0 )
      {
        v11 = "FsRtlSetKernelEaFile failed 0x%08lx\n";
        v12 = 647;
        goto LABEL_9;
      }
    }
    else
    {
      v10 = ZwSetEaFile(a4, &IoStatusBlock, v8, 0x37u);
      v9 = v10;
      if ( v10 < 0 )
      {
        v11 = "ZwSetEaFile failed 0x%08lx\n";
        v12 = 659;
        goto LABEL_9;
      }
    }
    v9 = 0;
    goto LABEL_15;
  }
  return 3221225480LL;
}

```

## disassembly

```asm
0x14003427c  mov     [rsp+arg_0], rcx
0x140034281  push    rbx
0x140034282  push    rsi
0x140034283  push    rdi
0x140034284  push    r14
0x140034286  sub     rsp, 48h
0x14003428a  mov     rbx, r9
0x14003428d  mov     rsi, rdx
0x140034290  test    rdx, rdx
0x140034293  jnz     short loc_14003429F
0x140034295  mov     eax, 0C00000F0h
0x14003429a  jmp     loc_140034404
0x14003429f  lea     rax, [r9-1]
0x1400342a3  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x1400342a7  ja      loc_1400343FF
0x1400342ad  mov     r14d, 1
0x1400342b3  xorps   xmm0, xmm0
0x1400342b6  mov     r8d, r14d
0x1400342b9  movups  xmmword ptr [rsp+68h+IoStatusBlock], xmm0
0x1400342be  lea     edx, [r14+36h]
0x1400342c2  call    AslAlloc
0x1400342c7  mov     rdi, rax
0x1400342ca  test    rax, rax
0x1400342cd  jnz     short loc_1400342D9
0x1400342cf  mov     ebx, 0C0000017h
0x1400342d4  jmp     loc_1400343FB
0x1400342d9  mov     dword ptr [rax], 0
0x1400342df  lea     rdx, aKernel; "$KERNEL."
0x1400342e6  mov     dword ptr [rax+4], 101B00h
0x1400342ed  lea     rcx, Str1; "$KERNEL.PURGE.AHC_READ_TIME"
0x1400342f4  movups  xmm0, xmmword ptr cs:Str1; "$KERNEL.PURGE.AHC_READ_TIME"
0x1400342fb  mov     r8d, 8; MaxCount
0x140034301  movups  xmmword ptr [rax+8], xmm0
0x140034305  movups  xmm1, xmmword ptr cs:Str1+0Bh; "GE.AHC_READ_TIME"
0x14003430c  movups  xmm0, xmmword ptr [rsi]
0x14003430f  movups  xmmword ptr [rax+13h], xmm1
0x140034313  mov     byte ptr [rax+23h], 0
0x140034317  movdqu  xmmword ptr [rax+24h], xmm0
0x14003431c  call    cs:__imp__strnicmp
0x140034323  nop     dword ptr [rax+rax+00h]
0x140034328  mov     rcx, rbx; FileHandle
0x14003432b  test    eax, eax
0x14003432d  jnz     loc_1400343C2
0x140034333  mov     r8, cs:__imp_IoFileObjectType
0x14003433a  lea     rax, [rsp+68h+arg_0]
0x14003433f  mov     [rsp+68h+HandleInformation], 0; HandleInformation
0x140034348  xor     r9d, r9d; AccessMode
0x14003434b  mov     edx, r14d; DesiredAccess
0x14003434e  mov     [rsp+68h+arg_0], 0
0x140034357  mov     [rsp+68h+Object], rax; Object
0x14003435c  mov     r8, [r8]; ObjectType
0x14003435f  call    cs:__imp_ObReferenceObjectByHandle
0x140034366  nop     dword ptr [rax+rax+00h]
0x14003436b  mov     ebx, eax
0x14003436d  test    eax, eax
0x14003436f  jns     short loc_140034393
0x140034371  lea     r9, aObreferenceobj; "ObReferenceObjectByHandle failed 0x%08l"...
0x140034378  mov     r8d, 27Fh
0x14003437e  lea     rdx, aAslfilesecsete_2; "AslFileSecSetEaByHandle"
0x140034385  mov     dword ptr [rsp+68h+Object], eax
0x140034389  mov     ecx, r14d
0x14003438c  call    AslLogCallPrintf
0x140034391  jmp     short loc_1400343F3
0x140034393  mov     rcx, [rsp+68h+arg_0]
0x140034398  mov     r8d, 37h ; '7'
0x14003439e  mov     rdx, rdi
0x1400343a1  call    cs:__imp_FsRtlSetKernelEaFile
0x1400343a8  nop     dword ptr [rax+rax+00h]
0x1400343ad  mov     ebx, eax
0x1400343af  test    eax, eax
0x1400343b1  jns     short loc_1400343F1
0x1400343b3  lea     r9, aFsrtlsetkernel; "FsRtlSetKernelEaFile failed 0x%08lx\n"
0x1400343ba  mov     r8d, 287h
0x1400343c0  jmp     short loc_14003437E
0x1400343c2  mov     r9d, 37h ; '7'; Length
0x1400343c8  lea     rdx, [rsp+68h+IoStatusBlock]; IoStatusBlock
0x1400343cd  mov     r8, rdi; Buffer
0x1400343d0  call    cs:__imp_ZwSetEaFile
0x1400343d7  nop     dword ptr [rax+rax+00h]
0x1400343dc  mov     ebx, eax
0x1400343de  test    eax, eax
0x1400343e0  jns     short loc_1400343F1
0x1400343e2  lea     r9, aZwseteafileFai; "ZwSetEaFile failed 0x%08lx\n"
0x1400343e9  mov     r8d, 293h
0x1400343ef  jmp     short loc_14003437E
0x1400343f1  xor     ebx, ebx
0x1400343f3  mov     rdx, rdi
0x1400343f6  call    AslFree
0x1400343fb  mov     eax, ebx
0x1400343fd  jmp     short loc_140034404
0x1400343ff  mov     eax, 0C0000008h
0x140034404  add     rsp, 48h
0x140034408  pop     r14
0x14003440a  pop     rdi
0x14003440b  pop     rsi
0x14003440c  pop     rbx
0x14003440d  retn
```
