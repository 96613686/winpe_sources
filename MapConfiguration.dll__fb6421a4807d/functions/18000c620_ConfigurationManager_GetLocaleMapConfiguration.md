# ConfigurationManager_GetLocaleMapConfiguration

- ea: `0x18000c620`
- end: `0x18000c6d5`
- name: `ConfigurationManager_GetLocaleMapConfiguration`
- size: `181`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callees

- `0x18000b4b8`
- `0x18000c410`
- `0x18000c620`
- `0x180043010`

## import_xrefs

- `ZTrace_Maps!ZTraceReportPropagationNoThis` at `0x18000c68b`
- `ZTrace_Maps!ZTraceReportPropagationNoThis` at `0x18000c68b`
- `ZTrace_Maps!ZTraceReportOriginationNoThis` at `0x18000c653`
- `ZTrace_Maps!ZTraceReportOriginationNoThis` at `0x18000c653`

## string_xrefs

- `0x18000c64c`: `ConfigurationManager_GetLocaleMapConfiguration`
- `0x18000c682`: `ConfigurationManager_GetLocaleMapConfiguration`

## pseudocode

```c
__int64 __fastcall ConfigurationManager_GetLocaleMapConfiguration(__int64 a1, __int64 a2, char a3, _QWORD *a4)
{
  int v8; // eax
  unsigned int v9; // ebx
  int v10; // eax
  __int64 v11; // r9
  int v12; // r8d
  __int64 v14; // [rsp+78h] [rbp+20h] BYREF

  v14 = 0;
  if ( a4 )
  {
    *a4 = 0;
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v14);
    v10 = ConfigurationManager_Create(&v14);
    if ( v10 >= 0 )
    {
      LOBYTE(v11) = a3;
      v10 = (*(__int64 (__fastcall **)(__int64, __int64, __int64, __int64, _QWORD *))(*(_QWORD *)v14 + 48LL))(
              v14,
              a1,
              a2,
              v11,
              a4);
      if ( v10 >= 0 )
      {
        v9 = 0;
        goto LABEL_10;
      }
      v12 = 108;
    }
    else
    {
      v12 = 107;
    }
    v8 = ZTraceReportPropagationNoThis(v10, "ConfigurationManager_GetLocaleMapConfiguration", v12);
  }
  else
  {
    v8 = ZTraceReportOriginationNoThis(-2147467261, "ConfigurationManager_GetLocaleMapConfiguration", 104);
  }
  v9 = v8;
LABEL_10:
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v14);
  return v9;
}

```

## disassembly

```asm
0x18000c620  push    rbx
0x18000c622  push    rbp
0x18000c623  push    rsi
0x18000c624  push    rdi
0x18000c625  sub     rsp, 38h
0x18000c629  mov     [rsp+58h+arg_18], 0
0x18000c632  mov     rbx, r9
0x18000c635  mov     dil, r8b
0x18000c638  mov     rsi, rdx
0x18000c63b  mov     rbp, rcx
0x18000c63e  test    r9, r9
0x18000c641  jnz     short loc_18000C65D
0x18000c643  lea     r8d, [r9+68h]
0x18000c647  mov     ecx, 80004003h
0x18000c64c  lea     rdx, aConfigurationm_3; "ConfigurationManager_GetLocaleMapConfig"...
0x18000c653  call    cs:__imp_?ZTraceReportOriginationNoThis@@YAJHPEBDH@Z; ZTraceReportOriginationNoThis(int,char const *,int)
0x18000c659  mov     ebx, eax
0x18000c65b  jmp     short loc_18000C6C0
0x18000c65d  lea     rcx, [rsp+58h+arg_18]
0x18000c662  mov     qword ptr [r9], 0
0x18000c669  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18000c66e  lea     rcx, [rsp+58h+arg_18]
0x18000c673  call    ConfigurationManager_Create
0x18000c678  test    eax, eax
0x18000c67a  jns     short loc_18000C693
0x18000c67c  mov     r8d, 6Bh ; 'k'
0x18000c682  lea     rdx, aConfigurationm_3; "ConfigurationManager_GetLocaleMapConfig"...
0x18000c689  mov     ecx, eax
0x18000c68b  call    cs:__imp_?ZTraceReportPropagationNoThis@@YAJHPEBDH@Z; ZTraceReportPropagationNoThis(int,char const *,int)
0x18000c691  jmp     short loc_18000C659
0x18000c693  mov     rcx, [rsp+58h+arg_18]
0x18000c698  mov     r9b, dil
0x18000c69b  mov     r8, rsi
0x18000c69e  mov     [rsp+58h+var_38], rbx
0x18000c6a3  mov     rdx, rbp
0x18000c6a6  mov     rax, [rcx]
0x18000c6a9  mov     rax, [rax+30h]
0x18000c6ad  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c6b2  test    eax, eax
0x18000c6b4  jns     short loc_18000C6BE
0x18000c6b6  mov     r8d, 6Ch ; 'l'
0x18000c6bc  jmp     short loc_18000C682
0x18000c6be  xor     ebx, ebx
0x18000c6c0  lea     rcx, [rsp+58h+arg_18]
0x18000c6c5  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18000c6ca  mov     eax, ebx
0x18000c6cc  add     rsp, 38h
0x18000c6d0  pop     rdi
0x18000c6d1  pop     rsi
0x18000c6d2  pop     rbp
0x18000c6d3  pop     rbx
0x18000c6d4  retn
```
