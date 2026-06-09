# imp_ApxDeviceCreate

- ea: `0x180010570`
- end: `0x1800107cc`
- name: `imp_ApxDeviceCreate`
- size: `604`
- prototype: `__int64 __fastcall(Apx::ApfVerify *this, Apx::ApfVerify *, Apx::ApfVerify *, Apx::ApfVerify *)`
- caller_count: `0`
- callee_count: `9`
- tags: `registry_config`

## callees

- `0x18000a12c`
- `0x18000a1b4`
- `0x18000a820`
- `0x18000a8e8`
- `0x18000a948`
- `0x18000ae48`
- `0x180010430`
- `0x180010570`
- `0x18002a010`

## string_xrefs

- `0x180010619`: `Config`
- `0x180010635`: `*Config`

## pseudocode

```c
__int64 __fastcall imp_ApxDeviceCreate(
        Apx::ApfVerify *this,
        Apx::ApfVerify *a2,
        Apx::ApfVerify *a3,
        Apx::ApfVerify *a4)
{
  Apx::ApfVerify *v8; // rcx
  int IsNull; // ebx
  struct APX_CLIENT_GLOBALS__ *v10; // rdx
  const unsigned __int16 *v11; // r8
  const unsigned __int16 *v12; // r8
  const unsigned __int16 *v13; // r8
  const unsigned __int16 *v14; // r8
  __int64 v15; // rdi
  _QWORD *v16; // rcx
  __int64 v17; // rdx
  struct Apx::ApfDevice *v18; // rdx
  struct Apx::ApfDevice *v20; // [rsp+20h] [rbp-48h] BYREF

  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 10, WPP_b7eae3fb092b37d2237e16ee9095a52e_Traceguids);
  }
  v20 = 0;
  IsNull = Apx::ApfVerify::IsNull(this, L"Globals", (const unsigned __int16 *)a3);
  if ( IsNull < 0 )
    goto LABEL_34;
  IsNull = Apx::ApfVerify::IsApxInitialized(v8);
  if ( IsNull < 0 )
    goto LABEL_34;
  IsNull = Apx::ApfVerify::ValidateClientBindings(this, v10);
  if ( IsNull < 0 )
    goto LABEL_34;
  IsNull = Apx::ApfVerify::IsNull(a2, L"Attributes", v11);
  if ( IsNull < 0 )
    goto LABEL_34;
  IsNull = Apx::ApfVerify::IsNotNull(a3, L"Config", v12);
  if ( IsNull < 0 )
    goto LABEL_34;
  IsNull = Apx::ApfVerify::IsNotNull(*(Apx::ApfVerify **)a3, L"*Config", v13);
  if ( IsNull < 0 )
    goto LABEL_34;
  IsNull = Apx::ApfVerify::IsNotNull(a4, L"Device", v14);
  if ( IsNull < 0 )
    goto LABEL_34;
  *(_QWORD *)a4 = 0;
  v15 = ~*(_QWORD *)a3;
  if ( (*(_BYTE *)(23LL - *(_QWORD *)a3) & 0x10) != 0 )
  {
    if ( (*(_BYTE *)(23LL - *(_QWORD *)a3) & 4) != 0 )
    {
      if ( (*(_BYTE *)(23LL - *(_QWORD *)a3) & 2) != 0 )
      {
        IsNull = Apx::ApfDevice::_CreateAndInitialize((struct Apx::ApfDeviceInit *)~*(_QWORD *)a3, &v20);
        if ( IsNull < 0 )
        {
          if ( v20 )
            (**(void (__fastcall ***)(struct Apx::ApfDevice *, __int64))v20)(v20, 1);
        }
        else
        {
          v18 = v20;
          *(_QWORD *)a4 = ~(unsigned __int64)v20;
          *(_QWORD *)(v15 + 16) = v18;
          *(_QWORD *)a3 = 0;
          if ( (*(_BYTE *)(v15 + 24) & 1) == 0 )
            (**(void (__fastcall ***)(__int64, __int64))v15)(v15, 1);
          IsNull = 0;
        }
        goto LABEL_34;
      }
      IsNull = -2147024809;
      v16 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control )
        return (unsigned int)IsNull;
      if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) == 0 || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
        goto LABEL_35;
      v17 = 13;
    }
    else
    {
      IsNull = -2147024809;
      v16 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control )
        return (unsigned int)IsNull;
      if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) == 0 || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
        goto LABEL_35;
      v17 = 12;
    }
LABEL_17:
    WPP_SF_d(v16[2], v17, WPP_b7eae3fb092b37d2237e16ee9095a52e_Traceguids);
LABEL_34:
    v16 = WPP_GLOBAL_Control;
    goto LABEL_35;
  }
  IsNull = -2147024809;
  v16 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control )
    return (unsigned int)IsNull;
  if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    v17 = 11;
    goto LABEL_17;
  }
LABEL_35:
  if ( v16 != &WPP_GLOBAL_Control && (*((_BYTE *)v16 + 28) & 1) != 0 && *((_BYTE *)v16 + 25) >= 5u )
    WPP_SF_(v16[2], 14, WPP_b7eae3fb092b37d2237e16ee9095a52e_Traceguids);
  return (unsigned int)IsNull;
}

```

## disassembly

```asm
0x180010570  push    rbx
0x180010572  push    rbp
0x180010573  push    rsi
0x180010574  push    rdi
0x180010575  push    r12
0x180010577  push    r14
0x180010579  sub     rsp, 38h
0x18001057d  mov     r14, r9
0x180010580  mov     rsi, r8
0x180010583  mov     rbp, rdx
0x180010586  mov     rdi, rcx
0x180010589  mov     rcx, cs:WPP_GLOBAL_Control
0x180010590  lea     r12, WPP_GLOBAL_Control
0x180010597  cmp     rcx, r12
0x18001059a  jz      short loc_1800105BD
0x18001059c  test    byte ptr [rcx+1Ch], 1
0x1800105a0  jz      short loc_1800105BD
0x1800105a2  cmp     byte ptr [rcx+19h], 5
0x1800105a6  jb      short loc_1800105BD
0x1800105a8  mov     rcx, [rcx+10h]
0x1800105ac  lea     r8, WPP_b7eae3fb092b37d2237e16ee9095a52e_Traceguids
0x1800105b3  mov     edx, 0Ah
0x1800105b8  call    WPP_SF_
0x1800105bd  lea     rdx, aGlobals; "Globals"
0x1800105c4  mov     [rsp+68h+var_48], 0
0x1800105cd  mov     rcx, rdi; this
0x1800105d0  call    ?IsNull@ApfVerify@Apx@@YAJPEBXPEBG@Z; Apx::ApfVerify::IsNull(void const *,ushort const *)
0x1800105d5  mov     ebx, eax
0x1800105d7  test    eax, eax
0x1800105d9  js      loc_180010790
0x1800105df  call    ?IsApxInitialized@ApfVerify@Apx@@YAJXZ; Apx::ApfVerify::IsApxInitialized(void)
0x1800105e4  mov     ebx, eax
0x1800105e6  test    eax, eax
0x1800105e8  js      loc_180010790
0x1800105ee  mov     rcx, rdi; this
0x1800105f1  call    ?ValidateClientBindings@ApfVerify@Apx@@YAJPEAUAPX_CLIENT_GLOBALS__@@@Z; Apx::ApfVerify::ValidateClientBindings(APX_CLIENT_GLOBALS__ *)
0x1800105f6  mov     ebx, eax
0x1800105f8  test    eax, eax
0x1800105fa  js      loc_180010790
0x180010600  lea     rdx, aAttributes; "Attributes"
0x180010607  mov     rcx, rbp; this
0x18001060a  call    ?IsNull@ApfVerify@Apx@@YAJPEBXPEBG@Z; Apx::ApfVerify::IsNull(void const *,ushort const *)
0x18001060f  mov     ebx, eax
0x180010611  test    eax, eax
0x180010613  js      loc_180010790
0x180010619  lea     rdx, aConfig_0; "Config"
0x180010620  mov     rcx, rsi; this
0x180010623  call    ?IsNotNull@ApfVerify@Apx@@YAJPEBXPEBG@Z; Apx::ApfVerify::IsNotNull(void const *,ushort const *)
0x180010628  mov     ebx, eax
0x18001062a  test    eax, eax
0x18001062c  js      loc_180010790
0x180010632  mov     rcx, [rsi]; this
0x180010635  lea     rdx, aConfig; "*Config"
0x18001063c  call    ?IsNotNull@ApfVerify@Apx@@YAJPEBXPEBG@Z; Apx::ApfVerify::IsNotNull(void const *,ushort const *)
0x180010641  mov     ebx, eax
0x180010643  test    eax, eax
0x180010645  js      loc_180010790
0x18001064b  lea     rdx, aDevice; "Device"
0x180010652  mov     rcx, r14; this
0x180010655  call    ?IsNotNull@ApfVerify@Apx@@YAJPEBXPEBG@Z; Apx::ApfVerify::IsNotNull(void const *,ushort const *)
0x18001065a  mov     ebx, eax
0x18001065c  test    eax, eax
0x18001065e  js      loc_180010790
0x180010664  mov     qword ptr [r14], 0
0x18001066b  mov     rdi, [rsi]
0x18001066e  not     rdi
0x180010671  test    byte ptr [rdi+18h], 10h
0x180010675  jnz     short loc_1800106BE
0x180010677  mov     r9d, 80070057h
0x18001067d  mov     ebx, r9d
0x180010680  mov     rcx, cs:WPP_GLOBAL_Control
0x180010687  cmp     rcx, r12
0x18001068a  jz      loc_1800107BD
0x180010690  test    byte ptr [rcx+1Ch], 40h
0x180010694  jz      loc_180010797
0x18001069a  cmp     byte ptr [rcx+19h], 2
0x18001069e  jb      loc_180010797
0x1800106a4  mov     edx, 0Bh
0x1800106a9  mov     rcx, [rcx+10h]
0x1800106ad  lea     r8, WPP_b7eae3fb092b37d2237e16ee9095a52e_Traceguids
0x1800106b4  call    WPP_SF_d
0x1800106b9  jmp     loc_180010790
0x1800106be  test    byte ptr [rdi+18h], 4
0x1800106c2  jnz     short loc_1800106F8
0x1800106c4  mov     r9d, 80070057h
0x1800106ca  mov     ebx, r9d
0x1800106cd  mov     rcx, cs:WPP_GLOBAL_Control
0x1800106d4  cmp     rcx, r12
0x1800106d7  jz      loc_1800107BD
0x1800106dd  test    byte ptr [rcx+1Ch], 40h
0x1800106e1  jz      loc_180010797
0x1800106e7  cmp     byte ptr [rcx+19h], 2
0x1800106eb  jb      loc_180010797
0x1800106f1  mov     edx, 0Ch
0x1800106f6  jmp     short loc_1800106A9
0x1800106f8  test    byte ptr [rdi+18h], 2
0x1800106fc  jnz     short loc_18001072D
0x1800106fe  mov     r9d, 80070057h
0x180010704  mov     ebx, r9d
0x180010707  mov     rcx, cs:WPP_GLOBAL_Control
0x18001070e  cmp     rcx, r12
0x180010711  jz      loc_1800107BD
0x180010717  test    byte ptr [rcx+1Ch], 40h
0x18001071b  jz      short loc_180010797
0x18001071d  cmp     byte ptr [rcx+19h], 2
0x180010721  jb      short loc_180010797
0x180010723  mov     edx, 0Dh
0x180010728  jmp     loc_1800106A9
0x18001072d  lea     rdx, [rsp+68h+var_48]; struct Apx::ApfDevice **
0x180010732  mov     rcx, rdi; struct Apx::ApfDeviceInit *
0x180010735  call    ?_CreateAndInitialize@ApfDevice@Apx@@SAJPEAVApfDeviceInit@2@PEAPEAV12@@Z; Apx::ApfDevice::_CreateAndInitialize(Apx::ApfDeviceInit *,Apx::ApfDevice * *)
0x18001073a  mov     ebx, eax
0x18001073c  test    eax, eax
0x18001073e  js      short loc_180010776
0x180010740  mov     rdx, [rsp+68h+var_48]
0x180010745  mov     rax, rdx
0x180010748  not     rax
0x18001074b  mov     [r14], rax
0x18001074e  mov     [rdi+10h], rdx
0x180010752  mov     qword ptr [rsi], 0
0x180010759  test    byte ptr [rdi+18h], 1
0x18001075d  jnz     short loc_180010772
0x18001075f  mov     rax, [rdi]
0x180010762  mov     edx, 1
0x180010767  mov     rcx, rdi
0x18001076a  mov     rax, [rax]
0x18001076d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010772  xor     ebx, ebx
0x180010774  jmp     short loc_180010790
0x180010776  mov     rcx, [rsp+68h+var_48]
0x18001077b  test    rcx, rcx
0x18001077e  jz      short loc_180010790
0x180010780  mov     rax, [rcx]
0x180010783  mov     edx, 1
0x180010788  mov     rax, [rax]
0x18001078b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010790  mov     rcx, cs:WPP_GLOBAL_Control
0x180010797  cmp     rcx, r12
0x18001079a  jz      short loc_1800107BD
0x18001079c  test    byte ptr [rcx+1Ch], 1
0x1800107a0  jz      short loc_1800107BD
0x1800107a2  cmp     byte ptr [rcx+19h], 5
0x1800107a6  jb      short loc_1800107BD
0x1800107a8  mov     rcx, [rcx+10h]
0x1800107ac  lea     r8, WPP_b7eae3fb092b37d2237e16ee9095a52e_Traceguids
0x1800107b3  mov     edx, 0Eh
0x1800107b8  call    WPP_SF_
0x1800107bd  mov     eax, ebx
0x1800107bf  add     rsp, 38h
0x1800107c3  pop     r14
0x1800107c5  pop     r12
0x1800107c7  pop     rdi
0x1800107c8  pop     rsi
0x1800107c9  pop     rbp
0x1800107ca  pop     rbx
0x1800107cb  retn
```
