# VsmUtils::AuthorizeSignCommand(VsmUtils::Vtl0KeyBlob *,tpm12class::TPMW8_Sign *,ushort const *,uchar *,uint)

- ea: `0x14005afe4`
- end: `0x14005b285`
- name: `?AuthorizeSignCommand@VsmUtils@@YAJPEAUVtl0KeyBlob@1@PEAVTPMW8_Sign@tpm12class@@PEBGPEAEI@Z`
- size: `673`
- prototype: `int(VsmUtils *__hidden this, struct VsmUtils::Vtl0KeyBlob *, struct tpm12class::TPMW8_Sign *, const unsigned __int16 *, unsigned __int8 *, unsigned int)`
- caller_count: `2`
- callee_count: `11`
- tags: `registry_config, broker_com_uri`

## callers

- `0x14005c700`
- `0x14005cb94`

## callees

- `0x140007410`
- `0x14000e034`
- `0x1400106dc`
- `0x1400107c4`
- `0x140055164`
- `0x14005ad84`
- `0x14005afe4`
- `0x1400624d4`
- `0x1400652d4`
- `0x140066174`
- `0x140068c88`

## import_xrefs

- `api-ms-win-core-heap-obsolete-l1-1-0!LocalFree` at `0x14005b0d0`
- `api-ms-win-core-heap-obsolete-l1-1-0!LocalFree` at `0x14005b22c`
- `api-ms-win-core-heap-obsolete-l1-1-0!LocalFree` at `0x14005b269`
- `api-ms-win-core-heap-obsolete-l1-1-0!LocalFree` at `0x14005b0d0`
- `api-ms-win-core-heap-obsolete-l1-1-0!LocalFree` at `0x14005b22c`
- `api-ms-win-core-heap-obsolete-l1-1-0!LocalFree` at `0x14005b269`

## string_xrefs

- `0x14005b049`: `onecore\ds\security\trustlet\utils\vtl1\lib\tpmhelper.cpp`
- `0x14005b0af`: `onecore\ds\security\trustlet\utils\vtl1\lib\tpmhelper.cpp`
- `0x14005b175`: `onecore\ds\security\trustlet\utils\vtl1\lib\tpmhelper.cpp`
- `0x14005b1e7`: `onecore\ds\security\trustlet\utils\vtl1\lib\tpmhelper.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall VsmUtils::AuthorizeSignCommand(
        VsmUtils *this,
        struct VsmUtils::Vtl0KeyBlob *a2,
        struct tpm12class::TPMW8_Sign *a3,
        const unsigned __int16 *a4,
        unsigned __int8 *a5)
{
  int SerializedParameters; // edi
  __int64 v10; // rdx
  int v12; // eax
  HLOCAL v13; // rcx
  __int64 v14; // r8
  int v15; // eax
  int v16; // eax
  unsigned int v17; // ebx
  HLOCAL v18; // rcx
  HLOCAL v19; // rcx
  int v20; // [rsp+20h] [rbp-C1h]
  void **v21; // [rsp+20h] [rbp-C1h]
  int v22; // [rsp+20h] [rbp-C1h]
  int v23; // [rsp+20h] [rbp-C1h]
  struct tpm12class::TPMW82B_BUFFER *v24; // [rsp+28h] [rbp-B9h]
  unsigned int v25; // [rsp+30h] [rbp-B1h]
  ULONG v26; // [rsp+38h] [rbp-A9h]
  HLOCAL hMem[2]; // [rsp+40h] [rbp-A1h] BYREF
  unsigned __int8 v28[8]; // [rsp+50h] [rbp-91h] BYREF
  __int64 v29; // [rsp+58h] [rbp-89h]
  __int64 v30; // [rsp+60h] [rbp-81h]
  int v31; // [rsp+68h] [rbp-79h]
  __int64 v32; // [rsp+70h] [rbp-71h]
  __int64 v33; // [rsp+78h] [rbp-69h]
  char v34; // [rsp+80h] [rbp-61h]
  __int16 v35; // [rsp+88h] [rbp-59h]
  __int64 v36; // [rsp+90h] [rbp-51h]
  unsigned int v37[36]; // [rsp+A0h] [rbp-41h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+138h] [rbp+57h]
  void **v39; // [rsp+148h] [rbp+67h] BYREF

  *(_WORD *)(*((_QWORD *)a2 + 21) + 762LL) = 11;
  *(_BYTE *)(*((_QWORD *)a2 + 21) + 761LL) = 1;
  SerializedParameters = tpm12class::TPMW8_SESSION::Create(*((tpm12class::TPMW8_SESSION **)a2 + 21), 0);
  if ( SerializedParameters < 0 )
  {
    v10 = 712;
LABEL_3:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v10,
      (unsigned int)"onecore\\ds\\security\\trustlet\\utils\\vtl1\\lib\\tpmhelper.cpp",
      (const char *)(unsigned int)SerializedParameters,
      v20);
    return (unsigned int)SerializedParameters;
  }
  LODWORD(v39) = 0;
  SerializedParameters = tpm12class::TPMW8_COMMAND::GetSerializedParameters(a2, (unsigned int *)&v39, 0);
  if ( SerializedParameters < 0 )
  {
    v10 = 717;
    goto LABEL_3;
  }
  wil::make_unique_hlocal<unsigned char [0]>(hMem, (unsigned int)v39);
  v12 = tpm12class::TPMW8_COMMAND::GetSerializedParameters(a2, (unsigned int *)&v39, (unsigned __int8 *)hMem[0]);
  SerializedParameters = v12;
  if ( v12 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x2D0,
      (unsigned int)"onecore\\ds\\security\\trustlet\\utils\\vtl1\\lib\\tpmhelper.cpp",
      (const char *)(unsigned int)v12,
      v20);
    goto LABEL_9;
  }
  `eh vector constructor iterator'(
    v37,
    0x48u,
    1u,
    (void (*)(void *))tpm12class::TPMW82B_BUFFER::TPMW82B_BUFFER,
    (void (*)(void *))tpm12class::TPMW82B_BUFFER::~TPMW82B_BUFFER);
  tpm12class::TPMW82B_BUFFER::CopyFrom((tpm12class::TPMW82B_BUFFER *)v37, (const unsigned __int8 *)this + 4, 0x22u);
  v29 = 0;
  v30 = 0;
  v31 = 0;
  v32 = 0;
  v33 = 0;
  v34 = 0;
  *(_QWORD *)v28 = &tpm12class::TPMW82B_BUFFER::`vftable';
  v35 = 0;
  v36 = 0;
  LODWORD(v21) = (_DWORD)v39;
  v15 = tpm12class::W8_ComputeCpHash((tpm12class *)v28, 0x15Du, v14, (__int64)v37, v21, (unsigned int)hMem[0], v28, v26);
  SerializedParameters = v15;
  if ( v15 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x2D8,
      (unsigned int)"onecore\\ds\\security\\trustlet\\utils\\vtl1\\lib\\tpmhelper.cpp",
      (const char *)(unsigned int)v15,
      v22);
    tpm12class::TPMW82B_BUFFER::~TPMW82B_BUFFER((tpm12class::TPMW82B_BUFFER *)v28);
    `eh vector destructor iterator'(v37, 0x48u, 1u, (void (*)(void *))tpm12class::TPMW82B_BUFFER::~TPMW82B_BUFFER);
LABEL_9:
    v13 = hMem[0];
    hMem[0] = 0;
    if ( v13 )
      LocalFree(v13);
    return (unsigned int)SerializedParameters;
  }
  LODWORD(v24) = *(_DWORD *)(*((_QWORD *)a2 + 21) + 16LL);
  v16 = VsmUtils::AuthorizePolicySecret(
          *((VsmUtils **)this + 5),
          (unsigned __int64)a3,
          a4,
          (unsigned __int8 *)(unsigned int)a5,
          (struct tpm12class::TPMW82B_BUFFER *)v28,
          v24,
          v25);
  v17 = v16;
  if ( v16 >= 0 )
  {
    tpm12class::TPMW82B_BUFFER::~TPMW82B_BUFFER((tpm12class::TPMW82B_BUFFER *)v28);
    `eh vector destructor iterator'(v37, 0x48u, 1u, (void (*)(void *))tpm12class::TPMW82B_BUFFER::~TPMW82B_BUFFER);
    v19 = hMem[0];
    hMem[0] = 0;
    if ( v19 )
      LocalFree(v19);
    return 0;
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x2DB,
      (unsigned int)"onecore\\ds\\security\\trustlet\\utils\\vtl1\\lib\\tpmhelper.cpp",
      (const char *)(unsigned int)v16,
      v23);
    tpm12class::TPMW82B_BUFFER::~TPMW82B_BUFFER((tpm12class::TPMW82B_BUFFER *)v28);
    `eh vector destructor iterator'(v37, 0x48u, 1u, (void (*)(void *))tpm12class::TPMW82B_BUFFER::~TPMW82B_BUFFER);
    v18 = hMem[0];
    hMem[0] = 0;
    if ( v18 )
      LocalFree(v18);
    return v17;
  }
}

```

## disassembly

```asm
0x14005afe4  push    rbp
0x14005afe6  push    rbx
0x14005afe7  push    rsi
0x14005afe8  push    rdi
0x14005afe9  push    r12
0x14005afeb  push    r13
0x14005afed  push    r14
0x14005afef  push    r15
0x14005aff1  lea     rbp, [rsp-17h]
0x14005aff6  sub     rsp, 0F8h
0x14005affd  mov     r14, r9
0x14005b000  mov     r15, r8
0x14005b003  mov     rbx, rdx
0x14005b006  mov     rsi, rcx
0x14005b009  mov     rax, [rdx+0A8h]
0x14005b010  mov     word ptr [rax+2FAh], 0Bh
0x14005b019  mov     rax, [rdx+0A8h]
0x14005b020  mov     r13d, 1
0x14005b026  mov     [rax+2F9h], r13b
0x14005b02d  xor     edx, edx; void *
0x14005b02f  mov     rcx, [rbx+0A8h]; this
0x14005b036  call    ?Create@TPMW8_SESSION@tpm12class@@QEAAJPEAX@Z; tpm12class::TPMW8_SESSION::Create(void *)
0x14005b03b  mov     edi, eax
0x14005b03d  xor     r12d, r12d
0x14005b040  test    eax, eax
0x14005b042  jns     short loc_14005B063
0x14005b044  mov     edx, 2C8h; void *
0x14005b049  lea     r8, aOnecoreDsSecur_27; "onecore\\ds\\security\\trustlet\\utils"...
0x14005b050  mov     r9d, edi; char *
0x14005b053  mov     rcx, [rbp+57h]; this
0x14005b057  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14005b05c  mov     eax, edi
0x14005b05e  jmp     loc_14005B271
0x14005b063  mov     dword ptr [rbp+4Fh+arg_8], r12d
0x14005b067  xor     r8d, r8d; unsigned __int8 *
0x14005b06a  lea     rdx, [rbp+4Fh+arg_8]; unsigned int *
0x14005b06e  mov     rcx, rbx; this
0x14005b071  call    ?GetSerializedParameters@TPMW8_COMMAND@tpm12class@@QEAAJPEAIPEAE@Z; tpm12class::TPMW8_COMMAND::GetSerializedParameters(uint *,uchar *)
0x14005b076  mov     edi, eax
0x14005b078  test    eax, eax
0x14005b07a  jns     short loc_14005B083
0x14005b07c  mov     edx, 2CDh
0x14005b081  jmp     short loc_14005B049
0x14005b083  mov     edx, dword ptr [rbp+4Fh+arg_8]
0x14005b086  lea     rcx, [rsp+130h+hMem]
0x14005b08b  call    ??$make_unique_hlocal@$$BY0A@E@wil@@YA?AV?$unique_ptr@$$BY0A@EU?$function_deleter@P6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@Z@wil@@@wistd@@_K@Z; wil::make_unique_hlocal<uchar [0]>(unsigned __int64)
0x14005b090  nop
0x14005b091  mov     r8, [rsp+130h+hMem]; unsigned __int8 *
0x14005b096  lea     rdx, [rbp+4Fh+arg_8]; unsigned int *
0x14005b09a  mov     rcx, rbx; this
0x14005b09d  call    ?GetSerializedParameters@TPMW8_COMMAND@tpm12class@@QEAAJPEAIPEAE@Z; tpm12class::TPMW8_COMMAND::GetSerializedParameters(uint *,uchar *)
0x14005b0a2  mov     edi, eax
0x14005b0a4  test    eax, eax
0x14005b0a6  jns     short loc_14005B0D8
0x14005b0a8  mov     rcx, [rbp+57h]; this
0x14005b0ac  mov     r9d, eax; char *
0x14005b0af  lea     r8, aOnecoreDsSecur_27; "onecore\\ds\\security\\trustlet\\utils"...
0x14005b0b6  mov     edx, 2D0h; void *
0x14005b0bb  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14005b0c0  nop
0x14005b0c1  mov     rcx, [rsp+130h+hMem]; hMem
0x14005b0c6  mov     [rsp+130h+hMem], r12
0x14005b0cb  test    rcx, rcx
0x14005b0ce  jz      short loc_14005B05C
0x14005b0d0  call    cs:__imp_LocalFree
0x14005b0d6  jmp     short loc_14005B05C
0x14005b0d8  lea     rax, ??1TPMW82B_BUFFER@tpm12class@@UEAA@XZ; tpm12class::TPMW82B_BUFFER::~TPMW82B_BUFFER(void)
0x14005b0df  mov     [rsp+130h+var_110], rax; void (*)(void *)
0x14005b0e4  lea     r9, ??0TPMW82B_BUFFER@tpm12class@@QEAA@XZ; void (*)(void *)
0x14005b0eb  mov     r8, r13; unsigned __int64
0x14005b0ee  mov     edx, 48h ; 'H'; unsigned __int64
0x14005b0f3  lea     rcx, [rbp+4Fh+var_90]; void *
0x14005b0f7  call    ??_L@YAXPEAX_K1P6AX0@Z2@Z; `eh vector constructor iterator'(void *,unsigned __int64,unsigned __int64,void (*)(void *),void (*)(void *))
0x14005b0fc  nop
0x14005b0fd  lea     rdx, [rsi+4]; unsigned __int8 *
0x14005b101  mov     r8d, 22h ; '"'; unsigned __int64
0x14005b107  lea     rcx, [rbp+4Fh+var_90]; this
0x14005b10b  call    ?CopyFrom@TPMW82B_BUFFER@tpm12class@@QEAAJPEBE_K@Z; tpm12class::TPMW82B_BUFFER::CopyFrom(uchar const *,unsigned __int64)
0x14005b110  mov     [rsp+130h+var_D8], r12
0x14005b115  mov     [rsp+130h+var_D0], r12
0x14005b11a  mov     [rbp+4Fh+var_C8], r12d
0x14005b11e  mov     [rbp+4Fh+var_C0], r12
0x14005b122  mov     [rbp+4Fh+var_B8], r12
0x14005b126  mov     [rbp+4Fh+var_B0], r12b
0x14005b12a  lea     rax, ??_7TPMW82B_BUFFER@tpm12class@@6B@; const tpm12class::TPMW82B_BUFFER::`vftable'
0x14005b131  mov     qword ptr [rsp+130h+var_E0], rax
0x14005b136  mov     [rbp+4Fh+var_A8], r12w
0x14005b13b  mov     [rbp+4Fh+var_A0], r12
0x14005b13f  mov     rax, [rsp+130h+hMem]
0x14005b144  lea     rcx, [rsp+130h+var_E0]; this
0x14005b149  mov     [rsp+130h+var_100], rcx; unsigned int
0x14005b14e  mov     [rsp+130h+var_108], rax; unsigned int
0x14005b153  mov     eax, dword ptr [rbp+4Fh+arg_8]
0x14005b156  mov     dword ptr [rsp+130h+var_110], eax; int
0x14005b15a  lea     r9, [rbp+4Fh+var_90]; unsigned int
0x14005b15e  mov     edx, 15Dh; unsigned __int16
0x14005b163  call    ?W8_ComputeCpHash@tpm12class@@YAJGIIQEAVTPMW82B_BUFFER@1@IPEBEPEAV21@2@Z; tpm12class::W8_ComputeCpHash(ushort,uint,uint,tpm12class::TPMW82B_BUFFER * const,uint,uchar const *,tpm12class::TPMW82B_BUFFER *,tpm12class::TPMW82B_BUFFER *)
0x14005b168  mov     edi, eax
0x14005b16a  test    eax, eax
0x14005b16c  jns     short loc_14005B1AF
0x14005b16e  mov     rcx, [rbp+57h]; this
0x14005b172  mov     r9d, eax; char *
0x14005b175  lea     r8, aOnecoreDsSecur_27; "onecore\\ds\\security\\trustlet\\utils"...
0x14005b17c  mov     edx, 2D8h; void *
0x14005b181  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14005b186  nop
0x14005b187  lea     rcx, [rsp+130h+var_E0]; this
0x14005b18c  call    ??1TPMW82B_BUFFER@tpm12class@@UEAA@XZ; tpm12class::TPMW82B_BUFFER::~TPMW82B_BUFFER(void)
0x14005b191  nop
0x14005b192  lea     r9, ??1TPMW82B_BUFFER@tpm12class@@UEAA@XZ; void (*)(void *)
0x14005b199  mov     r8, r13; unsigned __int64
0x14005b19c  mov     edx, 48h ; 'H'; unsigned __int64
0x14005b1a1  lea     rcx, [rbp+4Fh+var_90]; void *
0x14005b1a5  call    ??_M@YAXPEAX_K1P6AX0@Z@Z; `eh vector destructor iterator'(void *,unsigned __int64,unsigned __int64,void (*)(void *))
0x14005b1aa  jmp     loc_14005B0C1
0x14005b1af  mov     rax, [rbx+0A8h]
0x14005b1b6  mov     ecx, [rax+10h]
0x14005b1b9  mov     dword ptr [rsp+130h+var_108], ecx; struct tpm12class::TPMW82B_BUFFER *
0x14005b1bd  lea     rax, [rsp+130h+var_E0]
0x14005b1c2  mov     [rsp+130h+var_110], rax; int
0x14005b1c7  mov     r9d, dword ptr [rbp+4Fh+arg_20]; unsigned __int8 *
0x14005b1cb  mov     r8, r14; unsigned __int16 *
0x14005b1ce  mov     rdx, r15; unsigned __int64
0x14005b1d1  mov     rcx, [rsi+28h]; this
0x14005b1d5  call    ?AuthorizePolicySecret@VsmUtils@@YAJ_KPEBGPEAEIPEAVTPMW82B_BUFFER@tpm12class@@I@Z; VsmUtils::AuthorizePolicySecret(unsigned __int64,ushort const *,uchar *,uint,tpm12class::TPMW82B_BUFFER *,uint)
0x14005b1da  mov     ebx, eax
0x14005b1dc  test    eax, eax
0x14005b1de  jns     short loc_14005B236
0x14005b1e0  mov     rcx, [rbp+57h]; this
0x14005b1e4  mov     r9d, eax; char *
0x14005b1e7  lea     r8, aOnecoreDsSecur_27; "onecore\\ds\\security\\trustlet\\utils"...
0x14005b1ee  mov     edx, 2DBh; void *
0x14005b1f3  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14005b1f8  nop
0x14005b1f9  lea     rcx, [rsp+130h+var_E0]; this
0x14005b1fe  call    ??1TPMW82B_BUFFER@tpm12class@@UEAA@XZ; tpm12class::TPMW82B_BUFFER::~TPMW82B_BUFFER(void)
0x14005b203  nop
0x14005b204  lea     r9, ??1TPMW82B_BUFFER@tpm12class@@UEAA@XZ; void (*)(void *)
0x14005b20b  mov     r8, r13; unsigned __int64
0x14005b20e  mov     edx, 48h ; 'H'; unsigned __int64
0x14005b213  lea     rcx, [rbp+4Fh+var_90]; void *
0x14005b217  call    ??_M@YAXPEAX_K1P6AX0@Z@Z; `eh vector destructor iterator'(void *,unsigned __int64,unsigned __int64,void (*)(void *))
0x14005b21c  nop
0x14005b21d  mov     rcx, [rsp+130h+hMem]; hMem
0x14005b222  mov     [rsp+130h+hMem], r12
0x14005b227  test    rcx, rcx
0x14005b22a  jz      short loc_14005B232
0x14005b22c  call    cs:__imp_LocalFree
0x14005b232  mov     eax, ebx
0x14005b234  jmp     short loc_14005B271
0x14005b236  lea     rcx, [rsp+130h+var_E0]; this
0x14005b23b  call    ??1TPMW82B_BUFFER@tpm12class@@UEAA@XZ; tpm12class::TPMW82B_BUFFER::~TPMW82B_BUFFER(void)
0x14005b240  nop
0x14005b241  lea     r9, ??1TPMW82B_BUFFER@tpm12class@@UEAA@XZ; void (*)(void *)
0x14005b248  mov     r8, r13; unsigned __int64
0x14005b24b  mov     edx, 48h ; 'H'; unsigned __int64
0x14005b250  lea     rcx, [rbp+4Fh+var_90]; void *
0x14005b254  call    ??_M@YAXPEAX_K1P6AX0@Z@Z; `eh vector destructor iterator'(void *,unsigned __int64,unsigned __int64,void (*)(void *))
0x14005b259  nop
0x14005b25a  mov     rcx, [rsp+130h+hMem]; hMem
0x14005b25f  mov     [rsp+130h+hMem], r12
0x14005b264  test    rcx, rcx
0x14005b267  jz      short loc_14005B26F
0x14005b269  call    cs:__imp_LocalFree
0x14005b26f  xor     eax, eax
0x14005b271  add     rsp, 0F8h
0x14005b278  pop     r15
0x14005b27a  pop     r14
0x14005b27c  pop     r13
0x14005b27e  pop     r12
0x14005b280  pop     rdi
0x14005b281  pop     rsi
0x14005b282  pop     rbx
0x14005b283  pop     rbp
0x14005b284  retn
```
