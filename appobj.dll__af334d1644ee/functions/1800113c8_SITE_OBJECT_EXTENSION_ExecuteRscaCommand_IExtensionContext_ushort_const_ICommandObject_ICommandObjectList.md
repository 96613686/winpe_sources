# SITE_OBJECT_EXTENSION::ExecuteRscaCommand(IExtensionContext *,ushort const *,ICommandObject *,ICommandObjectList *)

- ea: `0x1800113c8`
- end: `0x180011688`
- name: `?ExecuteRscaCommand@SITE_OBJECT_EXTENSION@@AEAAJPEAVIExtensionContext@@PEBGPEAVICommandObject@@PEAVICommandObjectList@@@Z`
- size: `704`
- prototype: `__int64 __fastcall(SITE_OBJECT_EXTENSION *this, struct IExtensionContext *, const unsigned __int16 *, struct ICommandObject *, struct ICommandObjectList *)`
- caller_count: `1`
- callee_count: `7`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180011690`

## callees

- `0x180001044`
- `0x18000557c`
- `0x180006b6c`
- `0x1800113c8`
- `0x180011f30`
- `0x180034d00`
- `0x180036010`

## import_xrefs

- `msvcrt!_wcsicmp` at `0x180011526`
- `msvcrt!_wcsicmp` at `0x180011568`
- `msvcrt!_wcsicmp` at `0x1800115dd`
- `msvcrt!_wcsicmp` at `0x180011526`
- `msvcrt!_wcsicmp` at `0x180011568`
- `msvcrt!_wcsicmp` at `0x1800115dd`

## pseudocode

```c
__int64 __fastcall SITE_OBJECT_EXTENSION::ExecuteRscaCommand(
        SITE_OBJECT_EXTENSION *this,
        struct IExtensionContext *a2,
        const unsigned __int16 *a3,
        struct ICommandObject *a4,
        struct ICommandObjectList *a5)
{
  int v9; // ebx
  __int64 v10; // r8
  __int64 v11; // rdx
  int v12; // eax
  int v13; // eax
  int v14; // eax
  STATUS_OBJECT *v15; // rax
  const unsigned __int16 **v16; // rdi
  int v17; // eax
  unsigned int v19; // [rsp+30h] [rbp-40h] BYREF
  __int64 v20; // [rsp+38h] [rbp-38h] BYREF
  va_list v21; // [rsp+40h] [rbp-30h] BYREF
  __int64 v22; // [rsp+48h] [rbp-28h] BYREF
  va_list Arguments[2]; // [rsp+50h] [rbp-20h] BYREF
  __int64 v24; // [rsp+60h] [rbp-10h]

  v20 = 0;
  v24 = 0;
  v22 = 0;
  v19 = 0;
  v21 = 0;
  *(_OWORD *)Arguments = 0;
  if ( a2 && a3 && a4 && a5 )
  {
    if ( (int)SITE_OBJECT_EXTENSION::InitializeRSCA(this) < 0 )
    {
      v9 = -2147024846;
      v10 = 3221226535LL;
      v11 = 2147942450LL;
LABEL_7:
      (*(void (__fastcall **)(struct IExtensionContext *, __int64, __int64, va_list *, _DWORD))(*(_QWORD *)a2 + 144LL))(
        a2,
        v11,
        v10,
        Arguments,
        0);
      goto LABEL_29;
    }
    v9 = (*(__int64 (__fastcall **)(struct ICommandObject *, const unsigned __int16 *, va_list *))(*(_QWORD *)a4 + 80LL))(
           a4,
           L"SITE.NAME",
           &v21);
    if ( v9 >= 0 )
    {
      v9 = (*(__int64 (__fastcall **)(struct ICommandObject *, __int64 *))(*(_QWORD *)a4 + 48LL))(a4, &v22);
      if ( v9 >= 0 )
      {
        v9 = (*(__int64 (__fastcall **)(__int64, const wchar_t *, unsigned int *, _QWORD, _QWORD))(*(_QWORD *)v22 + 48LL))(
               v22,
               L"id",
               &v19,
               0,
               0);
        if ( v9 >= 0 )
        {
          v12 = (*(__int64 (__fastcall **)(_QWORD, _QWORD, __int64 *))(**((_QWORD **)this + 7) + 32LL))(
                  *((_QWORD *)this + 7),
                  v19,
                  &v20);
          v9 = v12;
          if ( v12 >= 0 )
          {
            if ( _wcsicmp(a3, L"START") )
            {
              if ( _wcsicmp(a3, L"STOP") )
              {
                v9 = -2147024846;
                goto LABEL_29;
              }
              v14 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v20 + 48LL))(v20);
              v11 = 2147943462LL;
              v9 = v14;
              if ( v14 == -2147023834 )
              {
                v10 = 3221226494LL;
                Arguments[0] = v21;
                goto LABEL_7;
              }
            }
            else
            {
              v13 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v20 + 40LL))(v20);
              v11 = 2147943456LL;
              v9 = v13;
              if ( v13 == -2147023840 )
              {
                v10 = 3221226493LL;
                Arguments[0] = v21;
                goto LABEL_7;
              }
            }
            if ( v9 >= 0 )
            {
              v15 = (STATUS_OBJECT *)operator new(0x110u);
              if ( v15 && (v16 = (const unsigned __int16 **)STATUS_OBJECT::STATUS_OBJECT(v15)) != 0 )
              {
                Arguments[0] = v21;
                v17 = _wcsicmp(a3, L"START");
                v9 = STATUS_OBJECT::Create(v16, (unsigned int)(v17 != 0) + 1025, Arguments);
                if ( v9 >= 0 )
                  v9 = (*(__int64 (__fastcall **)(struct ICommandObjectList *, const unsigned __int16 **))(*(_QWORD *)a5 + 24LL))(
                         a5,
                         v16);
                (*((void (__fastcall **)(const unsigned __int16 **))*v16 + 2))(v16);
              }
              else
              {
                v9 = -2147024888;
              }
            }
          }
          else
          {
            v11 = 2147942405LL;
            if ( v12 == -2147024891 )
            {
              v10 = 3221226495LL;
              goto LABEL_7;
            }
          }
        }
      }
    }
  }
  else
  {
    v9 = -2147024809;
  }
LABEL_29:
  if ( v20 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v20 + 16LL))(v20);
    v20 = 0;
  }
  if ( v22 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v22 + 16LL))(v22);
  return (unsigned int)v9;
}

```

## disassembly

```asm
0x1800113c8  push    rbp
0x1800113ca  push    rbx
0x1800113cb  push    rsi
0x1800113cc  push    rdi
0x1800113cd  push    r13
0x1800113cf  push    r14
0x1800113d1  push    r15
0x1800113d3  mov     rbp, rsp
0x1800113d6  sub     rsp, 70h
0x1800113da  mov     rax, cs:__security_cookie
0x1800113e1  xor     rax, rsp
0x1800113e4  mov     [rbp+var_8], rax
0x1800113e8  mov     r15, [rbp+arg_20]
0x1800113ec  xor     eax, eax
0x1800113ee  mov     [rbp+var_38], 0
0x1800113f6  xorps   xmm0, xmm0
0x1800113f9  mov     [rbp+var_10], rax
0x1800113fd  mov     rsi, r9
0x180011400  mov     [rbp+var_28], rax
0x180011404  mov     r14, r8
0x180011407  mov     [rbp+var_40], eax
0x18001140a  mov     rdi, rdx
0x18001140d  mov     [rbp+var_30], rax
0x180011411  mov     r13, rcx
0x180011414  movups  xmmword ptr [rbp+Arguments], xmm0
0x180011418  test    rdx, rdx
0x18001141b  jz      loc_180011634
0x180011421  test    r8, r8
0x180011424  jz      loc_180011634
0x18001142a  test    r9, r9
0x18001142d  jz      loc_180011634
0x180011433  test    r15, r15
0x180011436  jz      loc_180011634
0x18001143c  call    ?InitializeRSCA@SITE_OBJECT_EXTENSION@@AEAAJXZ; SITE_OBJECT_EXTENSION::InitializeRSCA(void)
0x180011441  test    eax, eax
0x180011443  jns     short loc_180011475
0x180011445  mov     ebx, 80070032h
0x18001144a  mov     r8d, 0C0000427h
0x180011450  mov     edx, ebx
0x180011452  mov     rax, [rdi]
0x180011455  lea     r9, [rbp+Arguments]
0x180011459  mov     rcx, rdi
0x18001145c  mov     dword ptr [rsp+70h+var_50], 0
0x180011464  mov     rax, [rax+90h]
0x18001146b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011470  jmp     loc_180011639
0x180011475  mov     rax, [rsi]
0x180011478  lea     r8, [rbp+var_30]
0x18001147c  lea     rdx, aSiteName; "SITE.NAME"
0x180011483  mov     rcx, rsi
0x180011486  mov     rax, [rax+50h]
0x18001148a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001148f  mov     ebx, eax
0x180011491  test    eax, eax
0x180011493  js      loc_180011639
0x180011499  mov     rax, [rsi]
0x18001149c  lea     rdx, [rbp+var_28]
0x1800114a0  mov     rcx, rsi
0x1800114a3  mov     rax, [rax+30h]
0x1800114a7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800114ac  mov     ebx, eax
0x1800114ae  test    eax, eax
0x1800114b0  js      loc_180011639
0x1800114b6  mov     rcx, [rbp+var_28]
0x1800114ba  lea     r8, [rbp+var_40]
0x1800114be  xor     r9d, r9d
0x1800114c1  mov     [rsp+70h+var_50], 0
0x1800114ca  lea     rdx, aId; "id"
0x1800114d1  mov     rax, [rcx]
0x1800114d4  mov     rax, [rax+30h]
0x1800114d8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800114dd  mov     ebx, eax
0x1800114df  test    eax, eax
0x1800114e1  js      loc_180011639
0x1800114e7  mov     rcx, [r13+38h]
0x1800114eb  lea     r8, [rbp+var_38]
0x1800114ef  mov     edx, [rbp+var_40]
0x1800114f2  mov     rax, [rcx]
0x1800114f5  mov     rax, [rax+20h]
0x1800114f9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800114fe  mov     ebx, eax
0x180011500  test    eax, eax
0x180011502  jns     short loc_18001151C
0x180011504  mov     edx, 80070005h
0x180011509  cmp     eax, edx
0x18001150b  jnz     loc_180011639
0x180011511  mov     r8d, 0C00003FFh
0x180011517  jmp     loc_180011452
0x18001151c  lea     rdx, aStart; "START"
0x180011523  mov     rcx, r14; String1
0x180011526  call    cs:__imp__wcsicmp
0x18001152c  test    eax, eax
0x18001152e  jnz     short loc_18001155E
0x180011530  mov     rcx, [rbp+var_38]
0x180011534  mov     rax, [rcx]
0x180011537  mov     rax, [rax+28h]
0x18001153b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011540  mov     edx, 80070420h
0x180011545  mov     ebx, eax
0x180011547  cmp     eax, edx
0x180011549  jnz     short loc_1800115A4
0x18001154b  mov     rax, [rbp+var_30]
0x18001154f  mov     r8d, 0C00003FDh
0x180011555  mov     [rbp+Arguments], rax
0x180011559  jmp     loc_180011452
0x18001155e  lea     rdx, aStop_0; "STOP"
0x180011565  mov     rcx, r14; String1
0x180011568  call    cs:__imp__wcsicmp
0x18001156e  test    eax, eax
0x180011570  jnz     loc_18001162D
0x180011576  mov     rcx, [rbp+var_38]
0x18001157a  mov     rax, [rcx]
0x18001157d  mov     rax, [rax+30h]
0x180011581  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011586  mov     edx, 80070426h
0x18001158b  mov     ebx, eax
0x18001158d  cmp     eax, edx
0x18001158f  jnz     short loc_1800115A4
0x180011591  mov     rax, [rbp+var_30]
0x180011595  mov     r8d, 0C00003FEh
0x18001159b  mov     [rbp+Arguments], rax
0x18001159f  jmp     loc_180011452
0x1800115a4  test    ebx, ebx
0x1800115a6  js      loc_180011639
0x1800115ac  mov     ecx, 110h; Size
0x1800115b1  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800115b6  test    rax, rax
0x1800115b9  jz      short loc_180011626
0x1800115bb  mov     rcx, rax; this
0x1800115be  call    ??0STATUS_OBJECT@@QEAA@XZ; STATUS_OBJECT::STATUS_OBJECT(void)
0x1800115c3  mov     rdi, rax
0x1800115c6  test    rax, rax
0x1800115c9  jz      short loc_180011626
0x1800115cb  mov     rax, [rbp+var_30]
0x1800115cf  lea     rdx, aStart; "START"
0x1800115d6  mov     rcx, r14; String1
0x1800115d9  mov     [rbp+Arguments], rax
0x1800115dd  call    cs:__imp__wcsicmp
0x1800115e3  lea     r8, [rbp+Arguments]; Arguments
0x1800115e7  mov     rcx, rdi; this
0x1800115ea  neg     eax
0x1800115ec  sbb     edx, edx
0x1800115ee  neg     edx
0x1800115f0  add     edx, 401h; dwMessageId
0x1800115f6  call    ?Create@STATUS_OBJECT@@QEAAJKQEAPEBG@Z; STATUS_OBJECT::Create(ulong,ushort const * * const)
0x1800115fb  mov     ebx, eax
0x1800115fd  test    eax, eax
0x1800115ff  js      short loc_180011615
0x180011601  mov     rax, [r15]
0x180011604  mov     rdx, rdi
0x180011607  mov     rcx, r15
0x18001160a  mov     rax, [rax+18h]
0x18001160e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011613  mov     ebx, eax
0x180011615  mov     rax, [rdi]
0x180011618  mov     rcx, rdi
0x18001161b  mov     rax, [rax+10h]
0x18001161f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011624  jmp     short loc_180011639
0x180011626  mov     ebx, 80070008h
0x18001162b  jmp     short loc_180011639
0x18001162d  mov     ebx, 80070032h
0x180011632  jmp     short loc_180011639
0x180011634  mov     ebx, 80070057h
0x180011639  mov     rcx, [rbp+var_38]
0x18001163d  test    rcx, rcx
0x180011640  jz      short loc_180011656
0x180011642  mov     rax, [rcx]
0x180011645  mov     rax, [rax+10h]
0x180011649  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001164e  mov     [rbp+var_38], 0
0x180011656  mov     rcx, [rbp+var_28]
0x18001165a  test    rcx, rcx
0x18001165d  jz      short loc_18001166B
0x18001165f  mov     rax, [rcx]
0x180011662  mov     rax, [rax+10h]
0x180011666  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001166b  mov     eax, ebx
0x18001166d  mov     rcx, [rbp+var_8]
0x180011671  xor     rcx, rsp; StackCookie
0x180011674  call    __security_check_cookie
0x180011679  add     rsp, 70h
0x18001167d  pop     r15
0x18001167f  pop     r14
0x180011681  pop     r13
0x180011683  pop     rdi
0x180011684  pop     rsi
0x180011685  pop     rbx
0x180011686  pop     rbp
0x180011687  retn
```
