# KerbPackData

- ea: `0x180001ea0`
- end: `0x18000207b`
- name: `KerbPackData`
- size: `475`
- prototype: ``
- caller_count: `9`
- callee_count: `4`
- tags: ``

## callers

- `0x180001c10`
- `0x180009fa0`
- `0x18000a3d0`
- `0x18000a650`
- `0x18000a920`
- `0x18000aed0`
- `0x18000b5b0`
- `0x18000bdf8`
- `0x18000c2d0`

## callees

- `0x180001ea0`
- `0x1800146ec`
- `0x1800283fc`
- `0x180029010`

## import_xrefs

- `MSASN1!ASN1_Encode` at `0x180001f0b`
- `MSASN1!ASN1_Encode` at `0x180001f0b`
- `MSASN1!ASN1_CloseEncoder` at `0x180001f73`
- `MSASN1!ASN1_CloseEncoder` at `0x180001f73`
- `MSASN1!ASN1_FreeEncoded` at `0x180001f56`
- `MSASN1!ASN1_FreeEncoded` at `0x180001f56`
- `MSASN1!ASN1_CreateEncoder` at `0x180001ee3`
- `MSASN1!ASN1_CreateEncoder` at `0x180001ee3`
- `MSASN1!ASN1_CreateModule` at `0x180001fff`
- `MSASN1!ASN1_CreateModule` at `0x180001fff`

## pseudocode

```c
__int64 __fastcall KerbPackData(__int64 a1, unsigned int a2, _DWORD *a3, _QWORD *a4)
{
  __int64 Module; // rax
  unsigned int Encoder; // eax
  int v10; // eax
  void *v11; // rax
  unsigned int v12; // ebx
  __int64 v13; // rcx
  int v14; // eax
  _QWORD v16[7]; // [rsp+50h] [rbp-38h] BYREF

  v16[0] = 0;
  if ( fKRB5ModuleStarted )
  {
    Module = KRB5_Module;
  }
  else
  {
    fKRB5ModuleStarted = 1;
    Module = ASN1_CreateModule(0x10000, 1024, 4096, 81, off_18002A2E0, off_18002A050, off_18002A570, L"\b", 895644267);
    KRB5_Module = Module;
  }
  Encoder = ASN1_CreateEncoder(Module, v16, 0, 0, 0);
  if ( !Encoder )
  {
    v10 = ASN1_Encode(v16[0], a1, a2, 16, 0, 0);
    if ( v10 >= 0 )
    {
      v11 = (void *)((__int64 (__fastcall *)(_QWORD))qword_1800334A0)(*(unsigned int *)(v16[0] + 28LL));
      *a4 = v11;
      if ( v11 )
      {
        v12 = 0;
        memcpy_0(v11, *(const void **)(v16[0] + 16LL), *(unsigned int *)(v16[0] + 28LL));
        v13 = v16[0];
        v14 = *(_DWORD *)(v16[0] + 28LL);
      }
      else
      {
        v13 = v16[0];
        v12 = 60;
        v14 = 0;
      }
      *a3 = v14;
      ASN1_FreeEncoded(v13, *(_QWORD *)(v13 + 16));
      goto LABEL_8;
    }
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        37,
        WPP_c655c859b2e13de8f31f421519d58447_Traceguids,
        (unsigned int)v10);
    goto LABEL_13;
  }
  if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
  {
LABEL_13:
    v12 = 60;
    goto LABEL_8;
  }
  WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 36, WPP_c655c859b2e13de8f31f421519d58447_Traceguids, Encoder);
  v12 = 60;
LABEL_8:
  if ( v16[0] )
    ASN1_CloseEncoder();
  return v12;
}

```

## disassembly

```asm
0x180001ea0  push    rbx
0x180001ea2  push    rbp
0x180001ea3  push    rsi
0x180001ea4  push    rdi
0x180001ea5  push    r14
0x180001ea7  sub     rsp, 60h
0x180001eab  xor     ebp, ebp
0x180001ead  mov     r14, r9
0x180001eb0  cmp     cs:?fKRB5ModuleStarted@@3HA, ebp; int fKRB5ModuleStarted
0x180001eb6  mov     rdi, r8
0x180001eb9  mov     ebx, edx
0x180001ebb  mov     [rsp+88h+var_38], rbp
0x180001ec0  mov     rsi, rcx
0x180001ec3  jz      loc_180001FA7
0x180001ec9  mov     rax, cs:KRB5_Module
0x180001ed0  xor     r9d, r9d
0x180001ed3  mov     [rsp+88h+var_68], rbp
0x180001ed8  xor     r8d, r8d
0x180001edb  lea     rdx, [rsp+88h+var_38]
0x180001ee0  mov     rcx, rax
0x180001ee3  call    cs:__imp_ASN1_CreateEncoder
0x180001ee9  test    eax, eax
0x180001eeb  jnz     loc_180002011
0x180001ef1  mov     rcx, [rsp+88h+var_38]
0x180001ef6  mov     r9d, 10h
0x180001efc  mov     dword ptr [rsp+88h+var_60], ebp
0x180001f00  mov     r8d, ebx
0x180001f03  mov     rdx, rsi
0x180001f06  mov     [rsp+88h+var_68], rbp
0x180001f0b  call    cs:__imp_ASN1_Encode
0x180001f11  test    eax, eax
0x180001f13  js      short loc_180001F89
0x180001f15  mov     rcx, [rsp+88h+var_38]
0x180001f1a  mov     rax, cs:qword_1800334A0
0x180001f21  mov     ecx, [rcx+1Ch]
0x180001f24  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001f29  mov     [r14], rax
0x180001f2c  test    rax, rax
0x180001f2f  jz      short loc_180001F7B
0x180001f31  mov     rdx, [rsp+88h+var_38]
0x180001f36  mov     rcx, rax; void *
0x180001f39  mov     ebx, ebp
0x180001f3b  mov     r8d, [rdx+1Ch]; Size
0x180001f3f  mov     rdx, [rdx+10h]; Src
0x180001f43  call    memcpy_0
0x180001f48  mov     rcx, [rsp+88h+var_38]
0x180001f4d  mov     eax, [rcx+1Ch]
0x180001f50  mov     [rdi], eax
0x180001f52  mov     rdx, [rcx+10h]
0x180001f56  call    cs:__imp_ASN1_FreeEncoded
0x180001f5c  mov     rcx, [rsp+88h+var_38]
0x180001f61  test    rcx, rcx
0x180001f64  jnz     short loc_180001F73
0x180001f66  mov     eax, ebx
0x180001f68  add     rsp, 60h
0x180001f6c  pop     r14
0x180001f6e  pop     rdi
0x180001f6f  pop     rsi
0x180001f70  pop     rbp
0x180001f71  pop     rbx
0x180001f72  retn
0x180001f73  call    cs:__imp_ASN1_CloseEncoder
0x180001f79  jmp     short loc_180001F66
0x180001f7b  mov     rcx, [rsp+88h+var_38]
0x180001f80  mov     ebx, 3Ch ; '<'
0x180001f85  mov     eax, ebp
0x180001f87  jmp     short loc_180001F50
0x180001f89  mov     rcx, cs:WPP_GLOBAL_Control
0x180001f90  lea     rdx, WPP_GLOBAL_Control
0x180001f97  cmp     rcx, rdx
0x180001f9a  jnz     loc_180002054
0x180001fa0  mov     ebx, 3Ch ; '<'
0x180001fa5  jmp     short loc_180001F5C
0x180001fa7  mov     [rsp+88h+var_48], 3562726Bh
0x180001faf  lea     rax, asc_18002D920; "\b"
0x180001fb6  mov     [rsp+88h+var_50], rax
0x180001fbb  mov     edx, 400h
0x180001fc0  lea     rax, off_18002A570
0x180001fc7  mov     cs:?fKRB5ModuleStarted@@3HA, 1; int fKRB5ModuleStarted
0x180001fd1  mov     [rsp+88h+var_58], rax
0x180001fd6  mov     r9d, 51h ; 'Q'
0x180001fdc  lea     rax, off_18002A050
0x180001fe3  mov     r8d, 1000h
0x180001fe9  mov     [rsp+88h+var_60], rax
0x180001fee  mov     ecx, 10000h
0x180001ff3  lea     rax, off_18002A2E0
0x180001ffa  mov     [rsp+88h+var_68], rax
0x180001fff  call    cs:__imp_ASN1_CreateModule
0x180002005  mov     cs:KRB5_Module, rax
0x18000200c  jmp     loc_180001ED0
0x180002011  mov     rcx, cs:WPP_GLOBAL_Control
0x180002018  lea     rdx, WPP_GLOBAL_Control
0x18000201f  cmp     rcx, rdx
0x180002022  jz      loc_180001FA0
0x180002028  test    byte ptr [rcx+1Ch], 1
0x18000202c  jz      loc_180001FA0
0x180002032  mov     rcx, [rcx+10h]
0x180002036  lea     r8, WPP_c655c859b2e13de8f31f421519d58447_Traceguids
0x18000203d  mov     edx, 24h ; '$'
0x180002042  mov     r9d, eax
0x180002045  call    WPP_SF_d
0x18000204a  mov     ebx, 3Ch ; '<'
0x18000204f  jmp     loc_180001F5C
0x180002054  test    byte ptr [rcx+1Ch], 1
0x180002058  jz      loc_180001FA0
0x18000205e  mov     rcx, [rcx+10h]
0x180002062  lea     r8, WPP_c655c859b2e13de8f31f421519d58447_Traceguids
0x180002069  mov     edx, 25h ; '%'
0x18000206e  mov     r9d, eax
0x180002071  call    WPP_SF_d
0x180002076  jmp     loc_180001FA0
```
