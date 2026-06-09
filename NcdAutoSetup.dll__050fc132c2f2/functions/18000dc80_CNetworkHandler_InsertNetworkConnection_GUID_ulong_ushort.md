# CNetworkHandler::_InsertNetworkConnection(_GUID,ulong,ushort *)

- ea: `0x18000dc80`
- end: `0x18000ded7`
- name: `?_InsertNetworkConnection@CNetworkHandler@@AEAAJU_GUID@@KPEAG@Z`
- size: `599`
- prototype: `__int64 __fastcall(CNetworkHandler *this, struct _GUID *, int, unsigned __int16 *)`
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x18000d978`

## callees

- `0x180001e6c`
- `0x18000a644`
- `0x18000d294`
- `0x18000d4e4`
- `0x18000dc80`
- `0x18000e374`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000de57`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000de57`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000dd46`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000de92`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000dd46`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000de92`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000dd07`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000de6b`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000dd07`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000de6b`

## pseudocode

```c
__int64 __fastcall CNetworkHandler::_InsertNetworkConnection(
        CNetworkHandler *this,
        struct _GUID *a2,
        int a3,
        unsigned __int16 *a4)
{
  unsigned __int16 *v4; // r15
  _QWORD *v8; // rcx
  struct _RTL_CRITICAL_SECTION *v9; // rbp
  int v10; // ebx
  _QWORD *v11; // r14
  _QWORD *v12; // rax
  _QWORD *v13; // rcx
  _QWORD *v14; // rax
  CNetworkHandler *v15; // rcx
  _QWORD *v16; // rbx
  LPVOID *v17; // rsi
  unsigned __int64 v18; // rdi
  _WORD *v19; // rdx
  unsigned __int64 v20; // rax
  unsigned __int64 v21; // rcx
  _WORD *v22; // rcx
  _QWORD *v23; // rax
  struct _GUID v25; // [rsp+30h] [rbp-48h]

  v4 = a4;
  v8 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x20) != 0 )
  {
    WPP_SF__guid_dS(*((_QWORD *)WPP_GLOBAL_Control + 2), (_DWORD)a2, a3, (_DWORD)a2, a3, (__int64)a4);
    v8 = WPP_GLOBAL_Control;
  }
  v25 = *a2;
  if ( v8 != &WPP_GLOBAL_Control && (*((_BYTE *)v8 + 28) & 0x20) != 0 )
    WPP_SF_(v8[2], 122, &WPP_e12904a7fb053f955c1ac70c1ea20c99_Traceguids);
  v9 = (struct _RTL_CRITICAL_SECTION *)((char *)this + 96);
  v10 = 0;
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 96));
  v11 = (_QWORD *)((char *)this + 80);
  v12 = (_QWORD *)*v11;
  if ( (_QWORD *)*v11 != v11 )
  {
    while ( *((_OWORD *)v12 + 1) != *(_OWORD *)&v25 || *((_DWORD *)v12 + 8) != a3 )
    {
      v12 = (_QWORD *)*v12;
      if ( v12 == v11 )
        goto LABEL_13;
    }
    v10 = 1;
  }
LABEL_13:
  LeaveCriticalSection(v9);
  v13 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x20) != 0 )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 123, &WPP_e12904a7fb053f955c1ac70c1ea20c99_Traceguids);
    v13 = WPP_GLOBAL_Control;
  }
  if ( !v10 )
  {
    v14 = operator new(0x50u, (const struct std::nothrow_t *)&std::nothrow);
    v16 = v14;
    if ( v14 )
    {
      v14[7] = 0;
      v14[8] = 0;
      v14[9] = 0;
      *((struct _GUID *)v14 + 1) = *a2;
      *((_DWORD *)v14 + 8) = a3;
      *(_QWORD *)((char *)v14 + 36) = 0;
      v14[6] = CNetworkHandler::_GetNetworkMask(v15, a3);
      v17 = (LPVOID *)(v16 + 7);
      if ( v4 )
      {
        v18 = -1;
        do
          ++v18;
        while ( v4[v18] );
        if ( (int)Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_EnsureCapacity(
                    (__int64)(v16 + 7),
                    v18) >= 0 )
        {
          v19 = *v17;
          v20 = v18 + 1;
          if ( v18 != -1 )
          {
            if ( v20 > 0x7FFFFFFF || v18 > 0x7FFFFFFE )
            {
              *v19 = 0;
            }
            else
            {
              v21 = v18;
              do
              {
                if ( !v21 )
                  break;
                if ( !*v4 )
                  break;
                *v19++ = *v4++;
                --v21;
                --v20;
              }
              while ( v20 );
              v22 = v19 - 1;
              if ( v20 )
                v22 = v19;
              *v22 = 0;
            }
          }
          v16[8] = v18;
        }
      }
      else
      {
        if ( *v17 )
        {
          CoTaskMemFree(*v17);
          *v17 = 0;
        }
        v16[8] = 0;
        v16[9] = 0;
      }
      EnterCriticalSection(v9);
      v23 = (_QWORD *)v11[1];
      if ( (_QWORD *)*v23 != v11 )
        __fastfail(3u);
      *v16 = v11;
      v16[1] = v23;
      *v23 = v16;
      v11[1] = v16;
      LeaveCriticalSection(v9);
    }
    v13 = WPP_GLOBAL_Control;
  }
  if ( v13 != &WPP_GLOBAL_Control && (*((_BYTE *)v13 + 28) & 0x20) != 0 )
    WPP_SF_(v13[2], 131, &WPP_e12904a7fb053f955c1ac70c1ea20c99_Traceguids);
  return 0;
}

```

## disassembly

```asm
0x18000dc80  push    rbx
0x18000dc82  push    rbp
0x18000dc83  push    rsi
0x18000dc84  push    rdi
0x18000dc85  push    r12
0x18000dc87  push    r14
0x18000dc89  push    r15
0x18000dc8b  sub     rsp, 40h
0x18000dc8f  mov     r15, r9
0x18000dc92  mov     edi, r8d
0x18000dc95  mov     rsi, rdx
0x18000dc98  mov     r14, rcx
0x18000dc9b  mov     rcx, cs:WPP_GLOBAL_Control
0x18000dca2  lea     rbx, WPP_GLOBAL_Control
0x18000dca9  cmp     rcx, rbx
0x18000dcac  jz      short loc_18000DCD1
0x18000dcae  test    byte ptr [rcx+1Ch], 20h
0x18000dcb2  jz      short loc_18000DCD1
0x18000dcb4  mov     rcx, [rcx+10h]
0x18000dcb8  mov     [rsp+78h+var_50], r9
0x18000dcbd  mov     r9, rdx
0x18000dcc0  mov     [rsp+78h+var_58], r8d
0x18000dcc5  call    WPP_SF__guid_dS
0x18000dcca  mov     rcx, cs:WPP_GLOBAL_Control
0x18000dcd1  movaps  xmm0, xmmword ptr [rsi]
0x18000dcd4  movdqa  [rsp+78h+var_48], xmm0
0x18000dcda  cmp     rcx, rbx
0x18000dcdd  jz      short loc_18000DCFA
0x18000dcdf  test    byte ptr [rcx+1Ch], 20h
0x18000dce3  jz      short loc_18000DCFA
0x18000dce5  mov     rcx, [rcx+10h]
0x18000dce9  lea     r8, WPP_e12904a7fb053f955c1ac70c1ea20c99_Traceguids
0x18000dcf0  mov     edx, 7Ah ; 'z'
0x18000dcf5  call    WPP_SF_
0x18000dcfa  lea     rbp, [r14+60h]
0x18000dcfe  xor     r12d, r12d
0x18000dd01  mov     rcx, rbp; lpCriticalSection
0x18000dd04  mov     ebx, r12d
0x18000dd07  call    cs:__imp_EnterCriticalSection
0x18000dd0d  add     r14, 50h ; 'P'
0x18000dd11  mov     rax, [r14]
0x18000dd14  cmp     rax, r14
0x18000dd17  jz      short loc_18000DD43
0x18000dd19  mov     rcx, qword ptr [rsp+78h+var_48+8]
0x18000dd1e  mov     rdx, qword ptr [rsp+78h+var_48]
0x18000dd23  cmp     [rax+10h], rdx
0x18000dd27  jnz     short loc_18000DD34
0x18000dd29  cmp     [rax+18h], rcx
0x18000dd2d  jnz     short loc_18000DD34
0x18000dd2f  cmp     [rax+20h], edi
0x18000dd32  jz      short loc_18000DD3E
0x18000dd34  mov     rax, [rax]
0x18000dd37  cmp     rax, r14
0x18000dd3a  jnz     short loc_18000DD23
0x18000dd3c  jmp     short loc_18000DD43
0x18000dd3e  mov     ebx, 1
0x18000dd43  mov     rcx, rbp; lpCriticalSection
0x18000dd46  call    cs:__imp_LeaveCriticalSection
0x18000dd4c  mov     rcx, cs:WPP_GLOBAL_Control
0x18000dd53  lea     rax, WPP_GLOBAL_Control
0x18000dd5a  cmp     rcx, rax
0x18000dd5d  jz      short loc_18000DD81
0x18000dd5f  test    byte ptr [rcx+1Ch], 20h
0x18000dd63  jz      short loc_18000DD81
0x18000dd65  mov     rcx, [rcx+10h]
0x18000dd69  lea     r8, WPP_e12904a7fb053f955c1ac70c1ea20c99_Traceguids
0x18000dd70  mov     edx, 7Bh ; '{'
0x18000dd75  call    WPP_SF_
0x18000dd7a  mov     rcx, cs:WPP_GLOBAL_Control
0x18000dd81  test    ebx, ebx
0x18000dd83  jnz     loc_18000DE9F
0x18000dd89  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18000dd90  lea     ecx, [rbx+50h]; unsigned __int64
0x18000dd93  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x18000dd98  mov     rbx, rax
0x18000dd9b  test    rax, rax
0x18000dd9e  jz      loc_18000DE98
0x18000dda4  mov     [rax+38h], r12
0x18000dda8  mov     edx, edi; unsigned int
0x18000ddaa  mov     [rax+40h], r12
0x18000ddae  mov     [rax+48h], r12
0x18000ddb2  movaps  xmm0, xmmword ptr [rsi]
0x18000ddb5  movdqu  xmmword ptr [rax+10h], xmm0
0x18000ddba  mov     [rax+20h], edi
0x18000ddbd  mov     [rax+24h], r12
0x18000ddc1  call    ?_GetNetworkMask@CNetworkHandler@@AEAA_KK@Z; CNetworkHandler::_GetNetworkMask(ulong)
0x18000ddc6  mov     [rbx+30h], rax
0x18000ddca  lea     rsi, [rbx+38h]
0x18000ddce  test    r15, r15
0x18000ddd1  jz      short loc_18000DE4F
0x18000ddd3  or      rdi, 0FFFFFFFFFFFFFFFFh
0x18000ddd7  inc     rdi
0x18000ddda  cmp     [r15+rdi*2], r12w
0x18000dddf  jnz     short loc_18000DDD7
0x18000dde1  mov     rdx, rdi
0x18000dde4  mov     rcx, rsi
0x18000dde7  call    ?_EnsureCapacity@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAJ_K@Z; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_EnsureCapacity(unsigned __int64)
0x18000ddec  test    eax, eax
0x18000ddee  js      short loc_18000DE68
0x18000ddf0  mov     rdx, [rsi]
0x18000ddf3  lea     rax, [rdi+1]
0x18000ddf7  test    rax, rax
0x18000ddfa  jz      short loc_18000DE49
0x18000ddfc  cmp     rax, 7FFFFFFFh
0x18000de02  ja      short loc_18000DE45
0x18000de04  cmp     rdi, 7FFFFFFEh
0x18000de0b  ja      short loc_18000DE45
0x18000de0d  mov     rcx, rdi
0x18000de10  test    rcx, rcx
0x18000de13  jz      short loc_18000DE34
0x18000de15  movzx   r8d, word ptr [r15]
0x18000de19  test    r8w, r8w
0x18000de1d  jz      short loc_18000DE34
0x18000de1f  mov     [rdx], r8w
0x18000de23  add     r15, 2
0x18000de27  add     rdx, 2
0x18000de2b  dec     rcx
0x18000de2e  sub     rax, 1
0x18000de32  jnz     short loc_18000DE10
0x18000de34  test    rax, rax
0x18000de37  lea     rcx, [rdx-2]
0x18000de3b  cmovnz  rcx, rdx
0x18000de3f  mov     [rcx], r12w
0x18000de43  jmp     short loc_18000DE49
0x18000de45  mov     [rdx], r12w
0x18000de49  mov     [rbx+40h], rdi
0x18000de4d  jmp     short loc_18000DE68
0x18000de4f  mov     rcx, [rsi]; pv
0x18000de52  test    rcx, rcx
0x18000de55  jz      short loc_18000DE60
0x18000de57  call    cs:__imp_CoTaskMemFree
0x18000de5d  mov     [rsi], r12
0x18000de60  mov     [rbx+40h], r12
0x18000de64  mov     [rbx+48h], r12
0x18000de68  mov     rcx, rbp; lpCriticalSection
0x18000de6b  call    cs:__imp_EnterCriticalSection
0x18000de71  mov     rax, [r14+8]
0x18000de75  cmp     [rax], r14
0x18000de78  jz      short loc_18000DE81
0x18000de7a  mov     ecx, 3
0x18000de7f  int     29h; Win8: RtlFailFast(ecx)
0x18000de81  mov     [rbx], r14
0x18000de84  mov     rcx, rbp; lpCriticalSection
0x18000de87  mov     [rbx+8], rax
0x18000de8b  mov     [rax], rbx
0x18000de8e  mov     [r14+8], rbx
0x18000de92  call    cs:__imp_LeaveCriticalSection
0x18000de98  mov     rcx, cs:WPP_GLOBAL_Control
0x18000de9f  lea     rax, WPP_GLOBAL_Control
0x18000dea6  cmp     rcx, rax
0x18000dea9  jz      short loc_18000DEC6
0x18000deab  test    byte ptr [rcx+1Ch], 20h
0x18000deaf  jz      short loc_18000DEC6
0x18000deb1  mov     rcx, [rcx+10h]
0x18000deb5  lea     r8, WPP_e12904a7fb053f955c1ac70c1ea20c99_Traceguids
0x18000debc  mov     edx, 83h
0x18000dec1  call    WPP_SF_
0x18000dec6  xor     eax, eax
0x18000dec8  add     rsp, 40h
0x18000decc  pop     r15
0x18000dece  pop     r14
0x18000ded0  pop     r12
0x18000ded2  pop     rdi
0x18000ded3  pop     rsi
0x18000ded4  pop     rbp
0x18000ded5  pop     rbx
0x18000ded6  retn
```
