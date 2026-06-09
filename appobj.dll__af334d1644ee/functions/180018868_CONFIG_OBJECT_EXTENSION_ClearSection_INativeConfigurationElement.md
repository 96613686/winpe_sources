# CONFIG_OBJECT_EXTENSION::ClearSection(INativeConfigurationElement *)

- ea: `0x180018868`
- end: `0x180018b72`
- name: `?ClearSection@CONFIG_OBJECT_EXTENSION@@AEAAJPEAVINativeConfigurationElement@@@Z`
- size: `778`
- prototype: `__int64 __fastcall(CONFIG_OBJECT_EXTENSION *__hidden this, struct INativeConfigurationElement *)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, loader_planting`

## callers

- `0x180019948`

## callees

- `0x180018868`
- `0x180034d00`
- `0x180036010`

## import_xrefs

- `OLEAUT32!__imp_SysAllocString` at `0x180018a8f`
- `OLEAUT32!__imp_SysAllocString` at `0x180018a8f`
- `OLEAUT32!__imp_SysFreeString` at `0x180018ad5`
- `OLEAUT32!__imp_SysFreeString` at `0x180018af7`
- `OLEAUT32!__imp_SysFreeString` at `0x180018ad5`
- `OLEAUT32!__imp_SysFreeString` at `0x180018af7`
- `OLEAUT32!__imp_VariantInit` at `0x1800188d5`
- `OLEAUT32!__imp_VariantInit` at `0x1800188d5`
- `OLEAUT32!__imp_VariantClear` at `0x180018ae9`
- `OLEAUT32!__imp_VariantClear` at `0x180018ae9`

## pseudocode

```c
__int64 __fastcall CONFIG_OBJECT_EXTENSION::ClearSection(
        CONFIG_OBJECT_EXTENSION *this,
        struct INativeConfigurationElement *a2)
{
  OLECHAR *v3; // rsi
  int v4; // ebx
  __int64 i; // r15
  int v6; // ecx
  int v7; // ecx
  int v8; // ecx
  unsigned int j; // r14d
  __int64 v10; // rax
  __int64 k; // rdi
  __int64 v12; // rdx
  __int64 *v14; // [rsp+20h] [rbp-E0h] BYREF
  unsigned int v15; // [rsp+28h] [rbp-D8h] BYREF
  unsigned int v16; // [rsp+2Ch] [rbp-D4h] BYREF
  __int64 v17; // [rsp+30h] [rbp-D0h] BYREF
  __int64 *v18; // [rsp+38h] [rbp-C8h] BYREF
  VARIANTARG pvarg; // [rsp+40h] [rbp-C0h] BYREF
  VARIANTARG v20; // [rsp+60h] [rbp-A0h] BYREF
  _DWORD v21[384]; // [rsp+80h] [rbp-80h] BYREF

  v15 = 64;
  v17 = 0;
  memset(&pvarg, 0, sizeof(pvarg));
  v14 = 0;
  v16 = 0;
  v3 = 0;
  v18 = 0;
  VariantInit(&pvarg);
  pvarg.vt = 0;
  if ( a2 )
  {
    v4 = (*(__int64 (__fastcall **)(struct INativeConfigurationElement *, _DWORD *, unsigned int *))(*(_QWORD *)a2 + 96LL))(
           a2,
           v21,
           &v15);
    if ( v4 >= 0 )
    {
      for ( i = 0; (unsigned int)i < v15; i = (unsigned int)(i + 1) )
      {
        v6 = v21[6 * i];
        if ( v6 )
        {
          v7 = v6 - 1;
          if ( v7 )
          {
            v8 = v7 - 1;
            if ( v8 && (unsigned int)(v8 - 1) > 1 )
            {
              v4 = -2147024883;
              goto LABEL_30;
            }
            v4 = (*(__int64 (__fastcall **)(struct INativeConfigurationElement *, __int64 **))(*(_QWORD *)a2 + 40LL))(
                   a2,
                   &v14);
            if ( v4 < 0 )
              goto LABEL_30;
            v4 = (*(__int64 (__fastcall **)(__int64 *, unsigned int *))(*v14 + 72))(v14, &v16);
            if ( v4 < 0 )
              goto LABEL_30;
            for ( j = 0; ; ++j )
            {
              v10 = *v14;
              if ( j >= v16 )
                break;
              v4 = (*(__int64 (__fastcall **)(__int64 *, _QWORD, _QWORD))(v10 + 96))(v14, v16 - j - 1, 0);
              if ( v4 < 0 )
                goto LABEL_30;
            }
            (*(void (**)(void))(v10 + 16))();
            v14 = 0;
          }
          else
          {
            v4 = (*(__int64 (__fastcall **)(struct INativeConfigurationElement *, _QWORD, __int64 *))(*(_QWORD *)a2 + 32LL))(
                   a2,
                   *(_QWORD *)&v21[6 * i + 2],
                   &v17);
            if ( v4 < 0 )
              goto LABEL_30;
            v4 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v17 + 168LL))(v17);
            if ( v4 < 0 )
              goto LABEL_30;
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v17 + 16LL))(v17);
            v17 = 0;
          }
        }
        else
        {
          v4 = (*(__int64 (__fastcall **)(struct INativeConfigurationElement *, _QWORD))(*(_QWORD *)a2 + 184LL))(
                 a2,
                 *(_QWORD *)&v21[6 * i + 2]);
          if ( v4 < 0 )
            goto LABEL_30;
        }
      }
      v4 = (**(__int64 (__fastcall ***)(struct INativeConfigurationElement *, GUID *, __int64 **))a2)(
             a2,
             &IID_IAppHostElement,
             &v18);
      if ( v4 >= 0 )
      {
        for ( k = 0; ; k = (unsigned int)(k + 1) )
        {
          v3 = 0;
          if ( (unsigned int)k >= 7 )
            break;
          v3 = SysAllocString((const OLECHAR *)(&g_apszBuiltInAttributes)[k]);
          if ( !v3 )
          {
            v4 = -2147024888;
            break;
          }
          v12 = *v18;
          v20 = pvarg;
          v4 = (*(__int64 (__fastcall **)(__int64 *, OLECHAR *, VARIANTARG *))(v12 + 64))(v18, v3, &v20);
          if ( v4 < 0 )
            break;
          SysFreeString(v3);
        }
      }
    }
  }
  else
  {
    v4 = -2147024809;
  }
LABEL_30:
  VariantClear(&pvarg);
  if ( v3 )
    SysFreeString(v3);
  if ( v18 )
  {
    (*(void (__fastcall **)(__int64 *))(*v18 + 16))(v18);
    v18 = 0;
  }
  if ( v14 )
  {
    (*(void (__fastcall **)(__int64 *))(*v14 + 16))(v14);
    v14 = 0;
  }
  if ( v17 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v17 + 16LL))(v17);
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x180018868  push    rbp
0x18001886a  push    rbx
0x18001886b  push    rsi
0x18001886c  push    rdi
0x18001886d  push    r14
0x18001886f  push    r15
0x180018871  lea     rbp, [rsp-598h]
0x180018879  sub     rsp, 698h
0x180018880  mov     rax, cs:__security_cookie
0x180018887  xor     rax, rsp
0x18001888a  mov     [rbp+5C0h+var_40], rax
0x180018891  xorps   xmm0, xmm0
0x180018894  mov     [rsp+6C0h+var_698], 40h ; '@'
0x18001889c  xor     eax, eax
0x18001889e  mov     [rsp+6C0h+var_690], 0
0x1800188a7  lea     rcx, [rsp+6C0h+pvarg]; pvarg
0x1800188ac  mov     qword ptr [rsp+6C0h+pvarg+10h], rax
0x1800188b1  movups  xmmword ptr [rsp+6C0h+pvarg], xmm0
0x1800188b6  mov     rdi, rdx
0x1800188b9  mov     [rsp+6C0h+var_6A0], 0
0x1800188c2  mov     [rsp+6C0h+var_694], 0
0x1800188ca  xor     esi, esi
0x1800188cc  mov     [rsp+6C0h+var_688], 0
0x1800188d5  call    cs:__imp_VariantInit
0x1800188db  xor     eax, eax
0x1800188dd  mov     word ptr [rsp+6C0h+pvarg], ax
0x1800188e2  test    rdi, rdi
0x1800188e5  jnz     short loc_1800188F1
0x1800188e7  mov     ebx, 80070057h
0x1800188ec  jmp     loc_180018AE4
0x1800188f1  mov     rax, [rdi]
0x1800188f4  lea     r8, [rsp+6C0h+var_698]
0x1800188f9  lea     rdx, [rbp+5C0h+var_640]
0x1800188fd  mov     rcx, rdi
0x180018900  mov     rax, [rax+60h]
0x180018904  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180018909  mov     ebx, eax
0x18001890b  test    eax, eax
0x18001890d  js      loc_180018AE4
0x180018913  xor     r15d, r15d
0x180018916  cmp     r15d, [rsp+6C0h+var_698]
0x18001891b  jnb     loc_180018A5B
0x180018921  lea     rdx, [r15+r15*2]
0x180018925  mov     ecx, [rbp+rdx*8+5C0h+var_640]
0x180018929  test    ecx, ecx
0x18001892b  jz      loc_180018A28
0x180018931  sub     ecx, 1
0x180018934  jz      loc_1800189CF
0x18001893a  sub     ecx, 1
0x18001893d  jz      short loc_18001894D
0x18001893f  sub     ecx, 1
0x180018942  jz      short loc_18001894D
0x180018944  cmp     ecx, 1
0x180018947  jnz     loc_180018A51
0x18001894d  mov     rax, [rdi]
0x180018950  lea     rdx, [rsp+6C0h+var_6A0]
0x180018955  mov     rcx, rdi
0x180018958  mov     rax, [rax+28h]
0x18001895c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180018961  mov     ebx, eax
0x180018963  test    eax, eax
0x180018965  js      loc_180018AE4
0x18001896b  mov     rcx, [rsp+6C0h+var_6A0]
0x180018970  lea     rdx, [rsp+6C0h+var_694]
0x180018975  mov     rax, [rcx]
0x180018978  mov     rax, [rax+48h]
0x18001897c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180018981  mov     ebx, eax
0x180018983  test    eax, eax
0x180018985  js      loc_180018AE4
0x18001898b  xor     r14d, r14d
0x18001898e  mov     rcx, [rsp+6C0h+var_6A0]
0x180018993  mov     edx, [rsp+6C0h+var_694]
0x180018997  mov     rax, [rcx]
0x18001899a  cmp     r14d, edx
0x18001899d  jnb     short loc_1800189BF
0x18001899f  mov     rax, [rax+60h]
0x1800189a3  sub     edx, r14d
0x1800189a6  dec     edx
0x1800189a8  xor     r8d, r8d
0x1800189ab  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800189b0  mov     ebx, eax
0x1800189b2  test    eax, eax
0x1800189b4  js      loc_180018AE4
0x1800189ba  inc     r14d
0x1800189bd  jmp     short loc_18001898E
0x1800189bf  mov     rax, [rax+10h]
0x1800189c3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800189c8  mov     [rsp+6C0h+var_6A0], rsi
0x1800189cd  jmp     short loc_180018A49
0x1800189cf  mov     rax, [rdi]
0x1800189d2  lea     r8, [rsp+6C0h+var_690]
0x1800189d7  mov     rdx, [rbp+rdx*8+5C0h+var_638]
0x1800189dc  mov     rcx, rdi
0x1800189df  mov     rax, [rax+20h]
0x1800189e3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800189e8  mov     ebx, eax
0x1800189ea  test    eax, eax
0x1800189ec  js      loc_180018AE4
0x1800189f2  mov     rcx, [rsp+6C0h+var_690]
0x1800189f7  mov     rax, [rcx]
0x1800189fa  mov     rax, [rax+0A8h]
0x180018a01  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180018a06  mov     ebx, eax
0x180018a08  test    eax, eax
0x180018a0a  js      loc_180018AE4
0x180018a10  mov     rcx, [rsp+6C0h+var_690]
0x180018a15  mov     rax, [rcx]
0x180018a18  mov     rax, [rax+10h]
0x180018a1c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180018a21  mov     [rsp+6C0h+var_690], rsi
0x180018a26  jmp     short loc_180018A49
0x180018a28  mov     rax, [rdi]
0x180018a2b  mov     rcx, rdi
0x180018a2e  mov     rdx, [rbp+rdx*8+5C0h+var_638]
0x180018a33  mov     rax, [rax+0B8h]
0x180018a3a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180018a3f  mov     ebx, eax
0x180018a41  test    eax, eax
0x180018a43  js      loc_180018AE4
0x180018a49  inc     r15d
0x180018a4c  jmp     loc_180018916
0x180018a51  mov     ebx, 8007000Dh
0x180018a56  jmp     loc_180018AE4
0x180018a5b  mov     rax, [rdi]
0x180018a5e  lea     r8, [rsp+6C0h+var_688]
0x180018a63  lea     rdx, IID_IAppHostElement
0x180018a6a  mov     rcx, rdi
0x180018a6d  mov     rax, [rax]
0x180018a70  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180018a75  mov     ebx, eax
0x180018a77  test    eax, eax
0x180018a79  js      short loc_180018AE4
0x180018a7b  xor     edi, edi
0x180018a7d  xor     esi, esi
0x180018a7f  cmp     edi, 7
0x180018a82  jnb     short loc_180018AE4
0x180018a84  lea     rax, ?g_apszBuiltInAttributes@@3PAPEBGA; ushort const * near * g_apszBuiltInAttributes
0x180018a8b  mov     rcx, [rax+rdi*8]; psz
0x180018a8f  call    cs:__imp_SysAllocString
0x180018a95  mov     rsi, rax
0x180018a98  test    rax, rax
0x180018a9b  jz      short loc_180018ADF
0x180018a9d  mov     rcx, [rsp+6C0h+var_688]
0x180018aa2  lea     r8, [rsp+6C0h+var_660]
0x180018aa7  movups  xmm0, xmmword ptr [rsp+6C0h+pvarg]
0x180018aac  movsd   xmm1, qword ptr [rsp+6C0h+pvarg+10h]
0x180018ab2  mov     rdx, [rcx]
0x180018ab5  movaps  [rsp+6C0h+var_660], xmm0
0x180018aba  movsd   [rsp+6C0h+var_650], xmm1
0x180018ac0  mov     rax, [rdx+40h]
0x180018ac4  mov     rdx, rsi
0x180018ac7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180018acc  mov     ebx, eax
0x180018ace  test    eax, eax
0x180018ad0  js      short loc_180018AE4
0x180018ad2  mov     rcx, rsi; bstrString
0x180018ad5  call    cs:__imp_SysFreeString
0x180018adb  inc     edi
0x180018add  jmp     short loc_180018A7D
0x180018adf  mov     ebx, 80070008h
0x180018ae4  lea     rcx, [rsp+6C0h+pvarg]; pvarg
0x180018ae9  call    cs:__imp_VariantClear
0x180018aef  test    rsi, rsi
0x180018af2  jz      short loc_180018AFD
0x180018af4  mov     rcx, rsi; bstrString
0x180018af7  call    cs:__imp_SysFreeString
0x180018afd  mov     rcx, [rsp+6C0h+var_688]
0x180018b02  test    rcx, rcx
0x180018b05  jz      short loc_180018B1C
0x180018b07  mov     rax, [rcx]
0x180018b0a  mov     rax, [rax+10h]
0x180018b0e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180018b13  mov     [rsp+6C0h+var_688], 0
0x180018b1c  mov     rcx, [rsp+6C0h+var_6A0]
0x180018b21  test    rcx, rcx
0x180018b24  jz      short loc_180018B3B
0x180018b26  mov     rax, [rcx]
0x180018b29  mov     rax, [rax+10h]
0x180018b2d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180018b32  mov     [rsp+6C0h+var_6A0], 0
0x180018b3b  mov     rcx, [rsp+6C0h+var_690]
0x180018b40  test    rcx, rcx
0x180018b43  jz      short loc_180018B51
0x180018b45  mov     rax, [rcx]
0x180018b48  mov     rax, [rax+10h]
0x180018b4c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180018b51  mov     eax, ebx
0x180018b53  mov     rcx, [rbp+5C0h+var_40]
0x180018b5a  xor     rcx, rsp; StackCookie
0x180018b5d  call    __security_check_cookie
0x180018b62  add     rsp, 698h
0x180018b69  pop     r15
0x180018b6b  pop     r14
0x180018b6d  pop     rdi
0x180018b6e  pop     rsi
0x180018b6f  pop     rbx
0x180018b70  pop     rbp
0x180018b71  retn
```
