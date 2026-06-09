# COMMAND_PROCESSOR::MatchCollectionElement(INativeConfigurationElement *,ulong,PARAMETER_LIST *,int *)

- ea: `0x18000aed4`
- end: `0x18000b0b3`
- name: `?MatchCollectionElement@COMMAND_PROCESSOR@@AEAAJPEAVINativeConfigurationElement@@KPEAVPARAMETER_LIST@@PEAH@Z`
- size: `479`
- prototype: `__int64 __fastcall(COMMAND_PROCESSOR *__hidden this, struct INativeConfigurationElement *, unsigned int, struct PARAMETER_LIST *, int *)`
- caller_count: `2`
- callee_count: `6`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18000774c`
- `0x180009aac`

## callees

- `0x180001fb0`
- `0x180004560`
- `0x18000aed4`
- `0x180034cbe`
- `0x180034d00`
- `0x180036010`

## import_xrefs

- `msvcrt!_wcsicmp` at `0x18000b05a`
- `msvcrt!_wcsicmp` at `0x18000b05a`

## pseudocode

```c
__int64 __fastcall COMMAND_PROCESSOR::MatchCollectionElement(
        COMMAND_PROCESSOR *this,
        struct INativeConfigurationElement *a2,
        __int64 a3,
        struct PARAMETER_LIST *a4,
        int *a5)
{
  unsigned int v7; // r12d
  int v8; // ebx
  unsigned int v9; // esi
  wchar_t *v10; // rdi
  __int64 v11; // rax
  int v12; // eax
  unsigned int v14; // [rsp+40h] [rbp-C0h] BYREF
  unsigned int v15; // [rsp+44h] [rbp-BCh] BYREF
  __int64 v16; // [rsp+48h] [rbp-B8h] BYREF
  wchar_t *String2; // [rsp+50h] [rbp-B0h] BYREF
  _BYTE v18[32]; // [rsp+58h] [rbp-A8h] BYREF
  wchar_t *p_String1; // [rsp+78h] [rbp-88h]
  int v20; // [rsp+80h] [rbp-80h]
  __int16 v21; // [rsp+84h] [rbp-7Ch]
  int v22; // [rsp+88h] [rbp-78h]
  wchar_t String1; // [rsp+90h] [rbp-70h] BYREF
  _BYTE v24[1022]; // [rsp+92h] [rbp-6Eh] BYREF

  v16 = 0;
  String2 = 0;
  memset_0(v24, 0, sizeof(v24));
  v21 = 256;
  p_String1 = &String1;
  v7 = 1024;
  v20 = 1024;
  v22 = 0;
  String1 = 0;
  v14 = 0;
  v15 = 0;
  if ( a2 && a4 && a5 )
  {
    *a5 = 0;
    v8 = 0;
    (*(void (__fastcall **)(struct PARAMETER_LIST *, unsigned int *))(*(_QWORD *)a4 + 24LL))(a4, &v15);
    v9 = 0;
    v10 = &String1;
    while ( v9 < v15 )
    {
      v8 = (*(__int64 (__fastcall **)(struct PARAMETER_LIST *, _QWORD, __int64 *, wchar_t **))(*(_QWORD *)a4 + 32LL))(
             a4,
             v9,
             &v16,
             &String2);
      if ( v8 < 0 )
        goto LABEL_17;
      v11 = *(_QWORD *)a2;
      v14 = v7;
      v12 = (*(__int64 (__fastcall **)(struct INativeConfigurationElement *, __int64, wchar_t *, unsigned int *, _QWORD, _QWORD))(v11 + 88))(
              a2,
              v16,
              v10,
              &v14,
              0,
              0);
      v8 = v12;
      if ( v12 < 0 )
      {
        if ( v12 != -2147024774 )
          goto LABEL_14;
        v8 = STRA::Resize((STRA *)v18, v14);
        if ( v8 < 0 )
          goto LABEL_17;
        v10 = p_String1;
        v8 = (*(__int64 (__fastcall **)(struct INativeConfigurationElement *, __int64, wchar_t *, unsigned int *, _QWORD, _QWORD))(*(_QWORD *)a2 + 88LL))(
               a2,
               v16,
               p_String1,
               &v14,
               0,
               0);
        if ( v8 < 0 )
        {
LABEL_14:
          v8 = 0;
          goto LABEL_17;
        }
        v7 = v20;
      }
      if ( _wcsicmp(v10, String2) )
        goto LABEL_17;
      ++v9;
    }
    *a5 = 1;
  }
  else
  {
    v8 = -2147024809;
  }
LABEL_17:
  BUFFER::~BUFFER((BUFFER *)v18);
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x18000aed4  mov     [rsp-8+arg_0], rbx
0x18000aed9  push    rbp
0x18000aeda  push    rsi
0x18000aedb  push    rdi
0x18000aedc  push    r12
0x18000aede  push    r13
0x18000aee0  push    r14
0x18000aee2  push    r15
0x18000aee4  lea     rbp, [rsp-3A0h]
0x18000aeec  sub     rsp, 4A0h
0x18000aef3  mov     rax, cs:__security_cookie
0x18000aefa  xor     rax, rsp
0x18000aefd  mov     [rbp+3D0h+var_40], rax
0x18000af04  mov     r15, [rbp+3D0h+arg_20]
0x18000af0b  lea     rcx, [rbp+3D0h+var_43E]; void *
0x18000af0f  mov     r13, rdx
0x18000af12  xor     edi, edi
0x18000af14  xor     edx, edx; Val
0x18000af16  mov     [rsp+4D0h+var_488], rdi
0x18000af1b  mov     r8d, 3FEh; Size
0x18000af21  mov     [rsp+4D0h+String2], rdi
0x18000af26  mov     r14, r9
0x18000af29  call    memset_0
0x18000af2e  mov     [rbp+3D0h+var_44C], 100h
0x18000af34  lea     rax, [rbp+3D0h+String1]
0x18000af38  mov     [rsp+4D0h+var_458], rax
0x18000af3d  mov     r12d, 400h
0x18000af43  mov     [rbp+3D0h+var_450], r12d
0x18000af47  mov     [rbp+3D0h+var_448], edi
0x18000af4a  mov     [rbp+3D0h+String1], di
0x18000af4e  mov     [rsp+4D0h+var_490], edi
0x18000af52  mov     [rsp+4D0h+var_48C], edi
0x18000af56  test    r13, r13
0x18000af59  jz      loc_18000B078
0x18000af5f  test    r14, r14
0x18000af62  jz      loc_18000B078
0x18000af68  test    r15, r15
0x18000af6b  jz      loc_18000B078
0x18000af71  mov     [r15], edi
0x18000af74  lea     rdx, [rsp+4D0h+var_48C]
0x18000af79  mov     rax, [r14]
0x18000af7c  mov     rcx, r14
0x18000af7f  mov     ebx, edi
0x18000af81  mov     rax, [rax+18h]
0x18000af85  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000af8a  mov     esi, edi
0x18000af8c  lea     rdi, [rbp+3D0h+String1]
0x18000af90  cmp     esi, [rsp+4D0h+var_48C]
0x18000af94  jnb     loc_18000B06F
0x18000af9a  mov     rax, [r14]
0x18000af9d  lea     r9, [rsp+4D0h+String2]
0x18000afa2  lea     r8, [rsp+4D0h+var_488]
0x18000afa7  mov     edx, esi
0x18000afa9  mov     rcx, r14
0x18000afac  mov     rax, [rax+20h]
0x18000afb0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000afb5  mov     ebx, eax
0x18000afb7  test    eax, eax
0x18000afb9  js      loc_18000B07D
0x18000afbf  mov     rax, [r13+0]
0x18000afc3  lea     r9, [rsp+4D0h+var_490]
0x18000afc8  mov     rdx, [rsp+4D0h+var_488]
0x18000afcd  mov     r8, rdi
0x18000afd0  mov     [rsp+4D0h+var_4A8], 0
0x18000afd9  mov     rcx, r13
0x18000afdc  mov     [rsp+4D0h+var_490], r12d
0x18000afe1  mov     rax, [rax+58h]
0x18000afe5  mov     [rsp+4D0h+var_4B0], 0
0x18000afee  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000aff3  mov     ebx, eax
0x18000aff5  test    eax, eax
0x18000aff7  jns     short loc_18000B052
0x18000aff9  cmp     eax, 8007007Ah
0x18000affe  jnz     short loc_18000B06B
0x18000b000  mov     edx, [rsp+4D0h+var_490]; unsigned int
0x18000b004  lea     rcx, [rsp+4D0h+var_478]; this
0x18000b009  call    ?Resize@STRA@@QEAAJK@Z; STRA::Resize(ulong)
0x18000b00e  mov     ebx, eax
0x18000b010  test    eax, eax
0x18000b012  js      short loc_18000B07D
0x18000b014  mov     rax, [r13+0]
0x18000b018  lea     r9, [rsp+4D0h+var_490]
0x18000b01d  mov     rdi, [rsp+4D0h+var_458]
0x18000b022  mov     rcx, r13
0x18000b025  mov     rdx, [rsp+4D0h+var_488]
0x18000b02a  mov     r8, rdi
0x18000b02d  mov     [rsp+4D0h+var_4A8], 0
0x18000b036  mov     rax, [rax+58h]
0x18000b03a  mov     [rsp+4D0h+var_4B0], 0
0x18000b043  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b048  mov     ebx, eax
0x18000b04a  test    eax, eax
0x18000b04c  js      short loc_18000B06B
0x18000b04e  mov     r12d, [rbp+3D0h+var_450]
0x18000b052  mov     rdx, [rsp+4D0h+String2]; String2
0x18000b057  mov     rcx, rdi; String1
0x18000b05a  call    cs:__imp__wcsicmp
0x18000b060  test    eax, eax
0x18000b062  jnz     short loc_18000B07D
0x18000b064  inc     esi
0x18000b066  jmp     loc_18000AF90
0x18000b06b  xor     ebx, ebx
0x18000b06d  jmp     short loc_18000B07D
0x18000b06f  mov     dword ptr [r15], 1
0x18000b076  jmp     short loc_18000B07D
0x18000b078  mov     ebx, 80070057h
0x18000b07d  lea     rcx, [rsp+4D0h+var_478]; this
0x18000b082  call    ??1BUFFER@@QEAA@XZ; BUFFER::~BUFFER(void)
0x18000b087  mov     eax, ebx
0x18000b089  mov     rcx, [rbp+3D0h+var_40]
0x18000b090  xor     rcx, rsp; StackCookie
0x18000b093  call    __security_check_cookie
0x18000b098  mov     rbx, [rsp+4D0h+arg_0]
0x18000b0a0  add     rsp, 4A0h
0x18000b0a7  pop     r15
0x18000b0a9  pop     r14
0x18000b0ab  pop     r13
0x18000b0ad  pop     r12
0x18000b0af  pop     rdi
0x18000b0b0  pop     rsi
0x18000b0b1  pop     rbp
0x18000b0b2  retn
```
