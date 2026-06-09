# VCabFileReader::cabFileStat(Vistream *,CabinetInfo *)

- ea: `0x180015760`
- end: `0x1800158c8`
- name: `?cabFileStat@VCabFileReader@@SAPEAVVstatus@@PEAVVistream@@PEAVCabinetInfo@@@Z`
- size: `360`
- prototype: `struct Vstatus *__fastcall(struct Vistream *, struct CabinetInfo *)`
- caller_count: `1`
- callee_count: `6`
- tags: ``

## callers

- `0x180016560`

## callees

- `0x180014190`
- `0x180014488`
- `0x180015760`
- `0x180083790`
- `0x1800b93d0`
- `0x1801503e0`

## import_xrefs

- `Cabinet!FDICreate` at `0x1800157e6`
- `Cabinet!FDICreate` at `0x1800157e6`
- `Cabinet!FDIIsCabinet` at `0x18001580a`
- `Cabinet!FDIIsCabinet` at `0x18001580a`
- `Cabinet!FDIDestroy` at `0x180015891`
- `Cabinet!FDIDestroy` at `0x180015891`
- `api-ms-win-crt-heap-l1-1-0!malloc` at `0x180015869`
- `api-ms-win-crt-heap-l1-1-0!malloc` at `0x180015869`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
struct Vstatus *__fastcall VCabFileReader::cabFileStat(struct Vistream *a1, struct CabinetInfo *a2)
{
  VgenericStatus *v4; // rbx
  HFDI v5; // r14
  __int64 v6; // rdi
  VgenericStatus *v7; // rax
  INT_PTR hf[10]; // [rsp+68h] [rbp-39h] BYREF
  FDICABINETINFO pfdici; // [rsp+B8h] [rbp+17h] BYREF
  ERF perf; // [rsp+D0h] [rbp+2Fh] BYREF

  v4 = 0;
  v5 = FDICreate(
         pfnalloc,
         pfnfree,
         sub_180016430,
         sub_180016520,
         sub_180016530,
         sub_180016540,
         (PFNSEEK)pfnseek,
         -1,
         &perf);
  sub_180014190(hf, a1, 0);
  if ( FDIIsCabinet(v5, (INT_PTR)hf, &pfdici) )
  {
    *(_DWORD *)a2 = pfdici.cbCabinet;
    *((_WORD *)a2 + 2) = pfdici.cFolders;
    *((_WORD *)a2 + 3) = pfdici.cFiles;
    *((_WORD *)a2 + 4) = pfdici.setID;
    *((_WORD *)a2 + 5) = pfdici.iCabinet;
    *((_BYTE *)a2 + 12) = pfdici.hasprev;
    *((_BYTE *)a2 + 13) = pfdici.hasnext;
    *((_QWORD *)a2 + 2) = a1;
  }
  else
  {
    v6 = *((_QWORD *)a1 + 1);
    if ( dword_1802B0018 )
      v7 = (VgenericStatus *)COWSAllocator::AllocCurrentHeap(0x20u);
    else
      v7 = (VgenericStatus *)malloc(0x20u);
    if ( v7 )
      v4 = VgenericStatus::VgenericStatus(v7, 0x2006Au, 0, v6);
  }
  FDIDestroy(v5);
  sub_180014488(hf);
  return v4;
}

```

## disassembly

```asm
0x180015760  mov     rax, rsp
0x180015763  push    rbp
0x180015764  push    rdi
0x180015765  push    r14
0x180015767  lea     rbp, [rax-5Fh]
0x18001576b  sub     rsp, 0E0h
0x180015772  mov     [rbp+57h+var_A0], 0FFFFFFFFFFFFFFFEh
0x18001577a  mov     [rax+18h], rbx
0x18001577e  mov     [rax+20h], rsi
0x180015782  mov     rax, cs:__security_cookie
0x180015789  xor     rax, rsp
0x18001578c  mov     [rbp+57h+var_18], rax
0x180015790  mov     rdi, rdx
0x180015793  mov     rsi, rcx
0x180015796  xor     ebx, ebx
0x180015798  lea     rax, [rbp+57h+var_28]
0x18001579c  mov     [rsp+0F0h+perf], rax; perf
0x1800157a1  or      dword ptr [rsp+0F0h+var_B8], 0FFFFFFFFh
0x1800157a6  lea     rax, pfnseek
0x1800157ad  mov     [rsp+0F0h+pfnseek], rax; pfnseek
0x1800157b2  lea     rax, sub_180016540
0x1800157b9  mov     [rsp+0F0h+pfnclose], rax; pfnclose
0x1800157be  lea     rax, sub_180016530
0x1800157c5  mov     [rsp+0F0h+pfnwrite], rax; pfnwrite
0x1800157ca  lea     r9, sub_180016520; pfnread
0x1800157d1  lea     r8, sub_180016430; pfnopen
0x1800157d8  lea     rdx, pfnfree; pfnfree
0x1800157df  lea     rcx, pfnalloc; pfnalloc
0x1800157e6  call    cs:FDICreate
0x1800157ec  mov     r14, rax
0x1800157ef  xor     r8d, r8d
0x1800157f2  mov     rdx, rsi
0x1800157f5  lea     rcx, [rbp+57h+hf]
0x1800157f9  call    sub_180014190
0x1800157fe  nop
0x1800157ff  lea     r8, [rbp+57h+pfdici]; pfdici
0x180015803  lea     rdx, [rbp+57h+hf]; hf
0x180015807  mov     rcx, r14; hfdi
0x18001580a  call    cs:FDIIsCabinet
0x180015810  test    al, al
0x180015812  jz      short loc_180015851
0x180015814  mov     eax, [rbp+57h+pfdici.cbCabinet]
0x180015817  mov     [rdi], eax
0x180015819  movzx   eax, [rbp+57h+pfdici.cFolders]
0x18001581d  mov     [rdi+4], ax
0x180015821  movzx   eax, [rbp+57h+pfdici.cFiles]
0x180015825  mov     [rdi+6], ax
0x180015829  movzx   eax, [rbp+57h+pfdici.setID]
0x18001582d  mov     [rdi+8], ax
0x180015831  movzx   eax, [rbp+57h+pfdici.iCabinet]
0x180015835  mov     [rdi+0Ah], ax
0x180015839  cmp     [rbp+57h+pfdici.hasprev], ebx
0x18001583c  setnz   al
0x18001583f  mov     [rdi+0Ch], al
0x180015842  cmp     [rbp+57h+pfdici.hasnext], ebx
0x180015845  setnz   al
0x180015848  mov     [rdi+0Dh], al
0x18001584b  mov     [rdi+10h], rsi
0x18001584f  jmp     short loc_18001588E
0x180015851  mov     rdi, [rsi+8]
0x180015855  mov     ecx, 20h ; ' '; unsigned __int64
0x18001585a  cmp     cs:dword_1802B0018, ebx
0x180015860  jz      short loc_180015869
0x180015862  call    ?AllocCurrentHeap@COWSAllocator@@SAPEAX_K@Z; COWSAllocator::AllocCurrentHeap(unsigned __int64)
0x180015867  jmp     short loc_18001586F
0x180015869  call    cs:malloc
0x18001586f  mov     [rbp+57h+var_98], rax
0x180015873  test    rax, rax
0x180015876  jz      short loc_18001588E
0x180015878  mov     r9, rdi
0x18001587b  xor     r8d, r8d; int
0x18001587e  mov     edx, 2006Ah; unsigned int
0x180015883  mov     rcx, rax; this
0x180015886  call    ??0VgenericStatus@@QEAA@KJZZ; VgenericStatus::VgenericStatus(ulong,long,...)
0x18001588b  mov     rbx, rax
0x18001588e  mov     rcx, r14; hfdi
0x180015891  call    cs:FDIDestroy
0x180015897  nop
0x180015898  lea     rcx, [rbp+57h+hf]
0x18001589c  call    sub_180014488
0x1800158a1  mov     rax, rbx
0x1800158a4  mov     rcx, [rbp+57h+var_18]
0x1800158a8  xor     rcx, rsp
0x1800158ab  call    sub_1801503E0
0x1800158b0  lea     r11, [rsp+0F0h+var_10]
0x1800158b8  mov     rbx, [r11+30h]
0x1800158bc  mov     rsi, [r11+38h]
0x1800158c0  mov     rsp, r11
0x1800158c3  pop     r14
0x1800158c5  pop     rdi
0x1800158c6  pop     rbp
0x1800158c7  retn
```
