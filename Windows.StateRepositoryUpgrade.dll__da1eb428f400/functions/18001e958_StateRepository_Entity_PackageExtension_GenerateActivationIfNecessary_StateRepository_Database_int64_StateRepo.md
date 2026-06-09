# StateRepository::Entity::PackageExtension::GenerateActivationIfNecessary(StateRepository::Database &,__int64 &,StateRepository::Entity::Activation *,StateRepository::ExecutionFlags)

- ea: `0x18001e958`
- end: `0x18001eb84`
- name: `?GenerateActivationIfNecessary@PackageExtension@Entity@StateRepository@@QEAAJAEAVDatabase@3@AEA_JPEAVActivation@23@W4ExecutionFlags@3@@Z`
- size: `556`
- prototype: `int __high(struct StateRepository::Database *, __int64 *, struct StateRepository::Entity::Activation *, enum StateRepository::ExecutionFlags)`
- caller_count: `1`
- callee_count: `12`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18000d734`

## callees

- `0x18000a3c0`
- `0x18000e0dc`
- `0x18000e194`
- `0x1800148ec`
- `0x180018f78`
- `0x18001e958`
- `0x18001eb8c`
- `0x18001ebc0`
- `0x180021f50`
- `0x180022080`
- `0x1800220c4`
- `0x18002212c`

## string_xrefs

- `0x18001e98d`: `onecore\base\appmodel\staterepository\dataaccesslayer\entity-packageextension-custom.cpp`
- `0x18001ea2e`: `onecore\base\appmodel\staterepository\dataaccesslayer\entity-packageextension-custom.cpp`

## pseudocode

```c
__int64 __fastcall StateRepository::Entity::PackageExtension::GenerateActivationIfNecessary(
        __int64 a1,
        StateRepository::Database *a2,
        _QWORD *a3)
{
  unsigned int v6; // ebx
  int v8; // ecx
  unsigned int v9; // eax
  unsigned int v10; // eax
  unsigned int TrustLevel; // eax
  int v12; // eax
  __int64 v13; // rdx
  unsigned int RuntimeBehavior; // eax
  unsigned int v15; // edx
  __int64 v16; // rdx
  __int64 v17; // rax
  int v18[8]; // [rsp+20h] [rbp-81h] BYREF
  unsigned int v19; // [rsp+40h] [rbp-61h]
  _BYTE v20[16]; // [rsp+48h] [rbp-59h] BYREF
  _BYTE v21[16]; // [rsp+58h] [rbp-49h] BYREF
  _BYTE v22[16]; // [rsp+68h] [rbp-39h] BYREF
  _BYTE v23[16]; // [rsp+78h] [rbp-29h] BYREF
  _BYTE v24[16]; // [rsp+88h] [rbp-19h] BYREF
  _BYTE v25[88]; // [rsp+98h] [rbp-9h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+F8h] [rbp+57h]

  *a3 = 0;
  if ( !StateRepository::Database::IsInAutoCommitMode(a2) )
  {
    if ( *(_QWORD *)(a1 + 56) )
      return 0;
    StateRepository::Entity::Activation::Activation((StateRepository::Entity::Activation *)v18);
    v8 = *(_DWORD *)(a1 + 144);
    if ( (v8 & 8) != 0 )
      v9 = v19 | 8;
    else
      v9 = v19 & 0xFFFFFFF7;
    if ( (v8 & 0x10000) != 0 )
      v10 = v9 | 0x40;
    else
      v10 = v9 & 0xFFFFFFBF;
    v19 = v10;
    TrustLevel = StateRepository::Entity::PackageExtension::GetTrustLevel(a1);
    v12 = StateRepository::Entity::Activation::SetTrustLevel(v18, TrustLevel);
    v6 = v12;
    if ( v12 >= 0 )
    {
      RuntimeBehavior = StateRepository::Entity::PackageExtension::GetRuntimeBehavior(a1);
      v12 = StateRepository::Entity::Activation::SetRuntimeBehavior(v18, RuntimeBehavior);
      v6 = v12;
      if ( v12 >= 0 )
      {
        v12 = StateRepository::Text::Set((StateRepository::Text *)v20, *(const unsigned __int16 **)(a1 + 64));
        v6 = v12;
        if ( v12 >= 0 )
        {
          v12 = StateRepository::Text::Set((StateRepository::Text *)v21, *(const unsigned __int16 **)(a1 + 80));
          v6 = v12;
          if ( v12 >= 0 )
          {
            v12 = StateRepository::Text::Set((StateRepository::Text *)v22, *(const unsigned __int16 **)(a1 + 96));
            v6 = v12;
            if ( v12 >= 0 )
            {
              v12 = StateRepository::Text::Set((StateRepository::Text *)v23, *(const unsigned __int16 **)(a1 + 112));
              v6 = v12;
              if ( v12 >= 0 )
              {
                v12 = StateRepository::Text::Set((StateRepository::Text *)v24, *(const unsigned __int16 **)(a1 + 128));
                v6 = v12;
                if ( v12 >= 0 )
                {
                  v12 = StateRepository::Text::Set((StateRepository::Text *)v25, *(const unsigned __int16 **)(a1 + 200));
                  v6 = v12;
                  if ( v12 >= 0 )
                  {
                    v15 = *(_DWORD *)(a1 + 144);
                    if ( (v15 & 0x20000) != 0 )
                      v16 = 1;
                    else
                      v16 = (v15 >> 17) & 2;
                    v12 = StateRepository::Entity::Activation::SetAppLifecycleBehavior(v18, v16);
                    v6 = v12;
                    if ( v12 >= 0 )
                    {
                      v12 = StateRepository::Entity::Activation::GetOrAddIfNotExist(v18, a2);
                      v6 = v12;
                      if ( v12 >= 0 )
                      {
                        v17 = *(_QWORD *)v18;
                        v6 = 0;
                        *(_QWORD *)(a1 + 56) = *(_QWORD *)v18;
                        *a3 = v17;
                        goto LABEL_36;
                      }
                      v13 = 320;
                    }
                    else
                    {
                      v13 = 319;
                    }
                  }
                  else
                  {
                    v13 = 318;
                  }
                }
                else
                {
                  v13 = 317;
                }
              }
              else
              {
                v13 = 316;
              }
            }
            else
            {
              v13 = 315;
            }
          }
          else
          {
            v13 = 314;
          }
        }
        else
        {
          v13 = 313;
        }
      }
      else
      {
        v13 = 312;
      }
    }
    else
    {
      v13 = 311;
    }
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v13,
      (unsigned int)"onecore\\base\\appmodel\\staterepository\\dataaccesslayer\\entity-packageextension-custom.cpp",
      (const char *)(unsigned int)v12,
      v18[0]);
LABEL_36:
    StateRepository::Entity::Activation::~Activation((StateRepository::Entity::Activation *)v18);
    return v6;
  }
  v6 = -2140733429;
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x12B,
    (unsigned int)"onecore\\base\\appmodel\\staterepository\\dataaccesslayer\\entity-packageextension-custom.cpp",
    (const char *)0x8067000BLL,
    v18[0]);
  return v6;
}

```

## disassembly

```asm
0x18001e958  push    rbp
0x18001e95a  push    rbx
0x18001e95b  push    rsi
0x18001e95c  push    rdi
0x18001e95d  push    r14
0x18001e95f  push    r15
0x18001e961  lea     rbp, [rsp-27h]
0x18001e966  sub     rsp, 0C8h
0x18001e96d  mov     rdi, rcx
0x18001e970  mov     qword ptr [r8], 0
0x18001e977  mov     rcx, rdx; this
0x18001e97a  mov     rsi, r8
0x18001e97d  mov     r14, rdx
0x18001e980  call    ?IsInAutoCommitMode@Database@StateRepository@@QEAA_NXZ; StateRepository::Database::IsInAutoCommitMode(void)
0x18001e985  test    al, al
0x18001e987  jz      short loc_18001E9AB
0x18001e989  mov     rcx, [rbp+57h]; this
0x18001e98d  lea     r8, aOnecoreBaseApp_60; "onecore\\base\\appmodel\\staterepositor"...
0x18001e994  mov     ebx, 8067000Bh
0x18001e999  mov     edx, 12Bh; void *
0x18001e99e  mov     r9d, ebx; char *
0x18001e9a1  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001e9a6  jmp     loc_18001EB72
0x18001e9ab  cmp     qword ptr [rdi+38h], 0
0x18001e9b0  jz      short loc_18001E9B9
0x18001e9b2  xor     eax, eax
0x18001e9b4  jmp     loc_18001EB74
0x18001e9b9  lea     rcx, [rsp+0F0h+var_D0]; this
0x18001e9be  call    ??0Activation@Entity@StateRepository@@QEAA@XZ; StateRepository::Entity::Activation::Activation(void)
0x18001e9c3  mov     ecx, [rdi+90h]
0x18001e9c9  mov     eax, [rbp+4Fh+var_B0]
0x18001e9cc  test    cl, 8
0x18001e9cf  jz      short loc_18001E9D6
0x18001e9d1  or      eax, 8
0x18001e9d4  jmp     short loc_18001E9D9
0x18001e9d6  and     eax, 0FFFFFFF7h
0x18001e9d9  bt      ecx, 10h
0x18001e9dd  jnb     short loc_18001E9E4
0x18001e9df  or      eax, 40h
0x18001e9e2  jmp     short loc_18001E9E7
0x18001e9e4  and     eax, 0FFFFFFBFh
0x18001e9e7  mov     rcx, rdi
0x18001e9ea  mov     [rbp+4Fh+var_B0], eax
0x18001e9ed  call    ?GetTrustLevel@PackageExtension@Entity@StateRepository@@QEBA?AW4SRTrustLevel@3@XZ; StateRepository::Entity::PackageExtension::GetTrustLevel(void)
0x18001e9f2  mov     edx, eax
0x18001e9f4  lea     rcx, [rsp+0F0h+var_D0]
0x18001e9f9  call    ?SetTrustLevel@Activation@Entity@StateRepository@@QEAAJW4SRTrustLevel@3@@Z; StateRepository::Entity::Activation::SetTrustLevel(StateRepository::SRTrustLevel)
0x18001e9fe  mov     ebx, eax
0x18001ea00  test    eax, eax
0x18001ea02  jns     short loc_18001EA0B
0x18001ea04  mov     edx, 137h
0x18001ea09  jmp     short loc_18001EA2A
0x18001ea0b  mov     rcx, rdi
0x18001ea0e  call    ?GetRuntimeBehavior@PackageExtension@Entity@StateRepository@@QEBA?AW4RuntimeBehavior@3@XZ; StateRepository::Entity::PackageExtension::GetRuntimeBehavior(void)
0x18001ea13  mov     edx, eax
0x18001ea15  lea     rcx, [rsp+0F0h+var_D0]
0x18001ea1a  call    ?SetRuntimeBehavior@Activation@Entity@StateRepository@@QEAAJW4RuntimeBehavior@3@@Z; StateRepository::Entity::Activation::SetRuntimeBehavior(StateRepository::RuntimeBehavior)
0x18001ea1f  mov     ebx, eax
0x18001ea21  test    eax, eax
0x18001ea23  jns     short loc_18001EA42
0x18001ea25  mov     edx, 138h; void *
0x18001ea2a  mov     rcx, [rbp+57h]; this
0x18001ea2e  lea     r8, aOnecoreBaseApp_60; "onecore\\base\\appmodel\\staterepositor"...
0x18001ea35  mov     r9d, eax; char *
0x18001ea38  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001ea3d  jmp     loc_18001EB68
0x18001ea42  mov     rdx, [rdi+40h]; unsigned __int16 *
0x18001ea46  lea     rcx, [rbp+4Fh+var_A8]; this
0x18001ea4a  mov     r15d, 100h
0x18001ea50  mov     r8d, r15d; unsigned __int64
0x18001ea53  call    ?Set@Text@StateRepository@@QEAAJPEBG_K@Z; StateRepository::Text::Set(ushort const *,unsigned __int64)
0x18001ea58  mov     ebx, eax
0x18001ea5a  test    eax, eax
0x18001ea5c  jns     short loc_18001EA64
0x18001ea5e  lea     edx, [r15+39h]
0x18001ea62  jmp     short loc_18001EA2A
0x18001ea64  mov     rdx, [rdi+50h]; unsigned __int16 *
0x18001ea68  lea     rcx, [rbp+4Fh+var_98]; this
0x18001ea6c  mov     r8, r15; unsigned __int64
0x18001ea6f  call    ?Set@Text@StateRepository@@QEAAJPEBG_K@Z; StateRepository::Text::Set(ushort const *,unsigned __int64)
0x18001ea74  mov     ebx, eax
0x18001ea76  test    eax, eax
0x18001ea78  jns     short loc_18001EA81
0x18001ea7a  mov     edx, 13Ah
0x18001ea7f  jmp     short loc_18001EA2A
0x18001ea81  mov     rdx, [rdi+60h]; unsigned __int16 *
0x18001ea85  lea     rcx, [rbp+4Fh+var_88]; this
0x18001ea89  mov     r8, r15; unsigned __int64
0x18001ea8c  call    ?Set@Text@StateRepository@@QEAAJPEBG_K@Z; StateRepository::Text::Set(ushort const *,unsigned __int64)
0x18001ea91  mov     ebx, eax
0x18001ea93  test    eax, eax
0x18001ea95  jns     short loc_18001EA9E
0x18001ea97  mov     edx, 13Bh
0x18001ea9c  jmp     short loc_18001EA2A
0x18001ea9e  mov     rdx, [rdi+70h]; unsigned __int16 *
0x18001eaa2  lea     rcx, [rbp+4Fh+var_78]; this
0x18001eaa6  mov     r8d, 0FFh; unsigned __int64
0x18001eaac  call    ?Set@Text@StateRepository@@QEAAJPEBG_K@Z; StateRepository::Text::Set(ushort const *,unsigned __int64)
0x18001eab1  mov     ebx, eax
0x18001eab3  test    eax, eax
0x18001eab5  jns     short loc_18001EAC1
0x18001eab7  mov     edx, 13Ch
0x18001eabc  jmp     loc_18001EA2A
0x18001eac1  mov     rdx, [rdi+80h]; unsigned __int16 *
0x18001eac8  lea     rcx, [rbp+4Fh+var_68]; this
0x18001eacc  mov     r8, r15; unsigned __int64
0x18001eacf  call    ?Set@Text@StateRepository@@QEAAJPEBG_K@Z; StateRepository::Text::Set(ushort const *,unsigned __int64)
0x18001ead4  mov     ebx, eax
0x18001ead6  test    eax, eax
0x18001ead8  jns     short loc_18001EAE4
0x18001eada  mov     edx, 13Dh
0x18001eadf  jmp     loc_18001EA2A
0x18001eae4  mov     rdx, [rdi+0C8h]; unsigned __int16 *
0x18001eaeb  lea     rcx, [rbp+4Fh+var_58]; this
0x18001eaef  mov     r8d, 0FFh; unsigned __int64
0x18001eaf5  call    ?Set@Text@StateRepository@@QEAAJPEBG_K@Z; StateRepository::Text::Set(ushort const *,unsigned __int64)
0x18001eafa  mov     ebx, eax
0x18001eafc  test    eax, eax
0x18001eafe  jns     short loc_18001EB0A
0x18001eb00  mov     edx, 13Eh
0x18001eb05  jmp     loc_18001EA2A
0x18001eb0a  mov     edx, [rdi+90h]
0x18001eb10  bt      edx, 11h
0x18001eb14  jnb     short loc_18001EB1D
0x18001eb16  mov     edx, 1
0x18001eb1b  jmp     short loc_18001EB23
0x18001eb1d  shr     edx, 11h
0x18001eb20  and     edx, 2
0x18001eb23  lea     rcx, [rsp+0F0h+var_D0]
0x18001eb28  call    ?SetAppLifecycleBehavior@Activation@Entity@StateRepository@@QEAAJW4AppLifecycleBehavior@3@@Z; StateRepository::Entity::Activation::SetAppLifecycleBehavior(StateRepository::AppLifecycleBehavior)
0x18001eb2d  mov     ebx, eax
0x18001eb2f  test    eax, eax
0x18001eb31  jns     short loc_18001EB3D
0x18001eb33  mov     edx, 13Fh
0x18001eb38  jmp     loc_18001EA2A
0x18001eb3d  mov     rdx, r14
0x18001eb40  lea     rcx, [rsp+0F0h+var_D0]
0x18001eb45  call    ?GetOrAddIfNotExist@Activation@Entity@StateRepository@@QEAAJAEAVDatabase@3@W4ExecutionFlags@3@@Z; StateRepository::Entity::Activation::GetOrAddIfNotExist(StateRepository::Database &,StateRepository::ExecutionFlags)
0x18001eb4a  mov     ebx, eax
0x18001eb4c  test    eax, eax
0x18001eb4e  jns     short loc_18001EB5A
0x18001eb50  mov     edx, 140h
0x18001eb55  jmp     loc_18001EA2A
0x18001eb5a  mov     rax, qword ptr [rsp+0F0h+var_D0]
0x18001eb5f  xor     ebx, ebx
0x18001eb61  mov     [rdi+38h], rax
0x18001eb65  mov     [rsi], rax
0x18001eb68  lea     rcx, [rsp+0F0h+var_D0]; this
0x18001eb6d  call    ??1Activation@Entity@StateRepository@@QEAA@XZ; StateRepository::Entity::Activation::~Activation(void)
0x18001eb72  mov     eax, ebx
0x18001eb74  add     rsp, 0C8h
0x18001eb7b  pop     r15
0x18001eb7d  pop     r14
0x18001eb7f  pop     rdi
0x18001eb80  pop     rsi
0x18001eb81  pop     rbx
0x18001eb82  pop     rbp
0x18001eb83  retn
```
