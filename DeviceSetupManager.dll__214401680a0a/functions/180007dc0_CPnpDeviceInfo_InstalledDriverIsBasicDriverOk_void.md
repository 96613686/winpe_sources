# CPnpDeviceInfo::InstalledDriverIsBasicDriverOk(void)

- ea: `0x180007dc0`
- end: `0x1800080e0`
- name: `?InstalledDriverIsBasicDriverOk@CPnpDeviceInfo@@QEAAHXZ`
- size: `800`
- prototype: `__int64 __fastcall(CPnpDeviceInfo *__hidden this)`
- caller_count: `2`
- callee_count: `8`
- tags: `service_task, installer_update, broker_com_uri`

## callers

- `0x18000f5f4`
- `0x1800346e8`

## callees

- `0x180007dc0`
- `0x1800080f0`
- `0x1800112a4`
- `0x18001af70`
- `0x18003f2d0`
- `0x18003f368`
- `0x1800419a0`
- `0x180045010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180007f9e`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180007f9e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180007ef5`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180007ef5`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180007fc7`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180007fe7`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180007fc7`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180007fe7`
- `api-ms-win-devices-query-l1-1-0!DevGetObjectProperties` at `0x180007e48`
- `api-ms-win-devices-query-l1-1-0!DevGetObjectProperties` at `0x180007e48`
- `api-ms-win-devices-query-l1-1-0!DevFreeObjectProperties` at `0x180007f4c`
- `api-ms-win-devices-query-l1-1-0!DevFreeObjectProperties` at `0x1800080b7`
- `api-ms-win-devices-query-l1-1-0!DevFreeObjectProperties` at `0x180007f4c`
- `api-ms-win-devices-query-l1-1-0!DevFreeObjectProperties` at `0x1800080b7`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall CPnpDeviceInfo::InstalledDriverIsBasicDriverOk(CPnpDeviceInfo *this)
{
  __int64 v2; // r14
  int ObjectProperties; // eax
  int v4; // r8d
  __int64 v5; // rcx
  LPVOID v6; // rdx
  LPVOID v7; // rax
  int v8; // edx
  const void *v9; // rsi
  size_t v10; // r15
  SIZE_T v11; // rbx
  char *v12; // rax
  char *v13; // rdi
  char *i; // rcx
  int v15; // r8d
  int ppv; // [rsp+20h] [rbp-49h]
  LPVOID pv; // [rsp+40h] [rbp-29h] BYREF
  LPVOID v19; // [rsp+48h] [rbp-21h] BYREF
  unsigned int v20; // [rsp+50h] [rbp-19h] BYREF
  DEVPROPKEY v21; // [rsp+58h] [rbp-11h] BYREF
  int v22; // [rsp+6Ch] [rbp+3h]
  __int64 v23; // [rsp+70h] [rbp+7h]
  wil::details::in1diag3 *retaddr; // [rsp+C8h] [rbp+5Fh]

  v20 = 0;
  v2 = *((_QWORD *)this + 1);
  pv = 0;
  LODWORD(v19) = 0;
  v21 = DEVPKEY_Device_DriverInfPath;
  v22 = 0;
  v23 = 0;
  ObjectProperties = DevGetObjectProperties(3, v2, 4, 1, &v21, &v19, &pv);
  if ( ObjectProperties >= 0 )
  {
    v5 = (unsigned int)v19;
    v7 = pv;
    if ( !(_DWORD)v19 )
      return v20;
    v8 = *((_DWORD *)pv + 8);
    if ( v8 )
    {
      if ( (_DWORD)v19 == 1 && v8 == 18 )
      {
        v9 = (const void *)*((_QWORD *)pv + 5);
        if ( v9 )
        {
          v10 = *((unsigned int *)pv + 9);
          v11 = (unsigned int)v10 & 0xFFFFFFFE;
          v12 = (char *)CoTaskMemAlloc(v11);
          v13 = v12;
          if ( v12 )
          {
            for ( i = v12; i != &v12[v11]; i += 2 )
              *(_WORD *)i = 0;
            memcpy_0(v12, v9, v10);
            if ( (_DWORD)v19 && pv )
              DevFreeObjectProperties((unsigned int)v19, pv);
            pv = 0;
            if ( (int)GetDeviceObjectStringProperty(3, *((_QWORD *)this + 1), &DEVPKEY_Device_MatchingDeviceId) >= 0 )
            {
              v19 = 0;
              if ( CoCreateInstance(
                     &GUID_6d93c83d_31c1_490e_b5f9_068a80e3d7cb,
                     0,
                     1u,
                     &GUID_612118c1_b1d3_4d55_80f2_4488b55cf623,
                     &v19) >= 0 )
                (*(void (__fastcall **)(LPVOID, char *, LPVOID, unsigned int *))(*(_QWORD *)v19 + 40LL))(
                  v19,
                  v13,
                  pv,
                  &v20);
              CoTaskMemFree(pv);
              if ( v19 )
                (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v19 + 16LL))(v19);
            }
            CoTaskMemFree(v13);
          }
          else
          {
            wil::details::in1diag3::Return_Hr(
              retaddr,
              (void *)0x8B,
              (unsigned int)"onecoreuap\\base\\devices\\setup\\lib\\utils\\dsmutils.cpp",
              (const char *)0x8007000ELL,
              ppv);
            if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
              WPP_SF__guid_dSd(
                *((_QWORD *)WPP_GLOBAL_Control + 2),
                13,
                v15,
                (unsigned int)&DEVPKEY_Device_DriverInfPath,
                5,
                v2,
                14);
            v5 = (unsigned int)v19;
            if ( (_DWORD)v19 )
            {
              v6 = pv;
              if ( pv )
                goto LABEL_39;
            }
          }
          return v20;
        }
      }
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      {
        WPP_SF__guid_dS(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          (unsigned int)&WPP_GLOBAL_Control,
          (_DWORD)WPP_GLOBAL_Control,
          (unsigned int)&DEVPKEY_Device_DriverInfPath,
          5,
          v2);
        v7 = pv;
        v5 = (unsigned int)v19;
      }
      if ( !(_DWORD)v5 || !v7 )
        return v20;
    }
    else if ( !pv )
    {
      return v20;
    }
    v6 = v7;
LABEL_39:
    DevFreeObjectProperties(v5, v6);
    return v20;
  }
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    WPP_SF__guid_dSd(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      11,
      v4,
      (unsigned int)&DEVPKEY_Device_DriverInfPath,
      5,
      v2,
      ObjectProperties);
  v5 = (unsigned int)v19;
  if ( (_DWORD)v19 )
  {
    v6 = pv;
    if ( pv )
      goto LABEL_39;
  }
  return v20;
}

```

## disassembly

```asm
0x180007dc0  push    rbp
0x180007dc2  push    rbx
0x180007dc3  push    rsi
0x180007dc4  push    rdi
0x180007dc5  push    r12
0x180007dc7  push    r13
0x180007dc9  push    r14
0x180007dcb  push    r15
0x180007dcd  lea     rbp, [rsp-1Fh]
0x180007dd2  sub     rsp, 88h
0x180007dd9  mov     rax, cs:__security_cookie
0x180007de0  xor     rax, rsp
0x180007de3  mov     [rbp+57h+var_48], rax
0x180007de7  mov     r13, rcx
0x180007dea  xor     r12d, r12d
0x180007ded  mov     [rbp+57h+var_70], r12d
0x180007df1  mov     r14, [rcx+8]
0x180007df5  mov     [rbp+57h+pv], r12
0x180007df9  mov     dword ptr [rbp+57h+var_78], r12d
0x180007dfd  movups  xmm0, xmmword ptr cs:DEVPKEY_Device_DriverInfPath.fmtid.Data1
0x180007e04  movups  xmmword ptr [rbp+57h+var_68], xmm0
0x180007e08  mov     eax, cs:DEVPKEY_Device_DriverInfPath.pid
0x180007e0e  mov     [rbp+57h+var_58], eax
0x180007e11  mov     [rbp+57h+var_54], r12d
0x180007e15  mov     [rbp+57h+var_50], r12
0x180007e19  lea     rax, [rbp+57h+pv]
0x180007e1d  mov     [rsp+0C0h+var_90], rax
0x180007e22  lea     rax, [rbp+57h+var_78]
0x180007e26  mov     [rsp+0C0h+var_98], rax
0x180007e2b  lea     rax, [rbp+57h+var_68]
0x180007e2f  mov     [rsp+0C0h+ppv], rax; int
0x180007e34  mov     r9d, 1
0x180007e3a  mov     r8d, 4
0x180007e40  mov     rdx, r14
0x180007e43  mov     ecx, 3
0x180007e48  call    cs:__imp_DevGetObjectProperties
0x180007e4e  test    eax, eax
0x180007e50  jns     short loc_180007EAE
0x180007e52  lea     rdx, WPP_GLOBAL_Control
0x180007e59  mov     rcx, cs:WPP_GLOBAL_Control
0x180007e60  cmp     rcx, rdx
0x180007e63  jz      short loc_180007E91
0x180007e65  test    byte ptr [rcx+1Ch], 1
0x180007e69  jz      short loc_180007E91
0x180007e6b  mov     edx, 0Bh
0x180007e70  mov     dword ptr [rsp+0C0h+var_90], eax
0x180007e74  mov     [rsp+0C0h+var_98], r14
0x180007e79  mov     dword ptr [rsp+0C0h+ppv], 5
0x180007e81  lea     r9, DEVPKEY_Device_DriverInfPath
0x180007e88  mov     rcx, [rcx+10h]
0x180007e8c  call    WPP_SF__guid_dSd
0x180007e91  mov     ecx, dword ptr [rbp+57h+var_78]
0x180007e94  test    ecx, ecx
0x180007e96  jz      loc_1800080BD
0x180007e9c  mov     rdx, [rbp+57h+pv]
0x180007ea0  test    rdx, rdx
0x180007ea3  jz      loc_1800080BD
0x180007ea9  jmp     loc_1800080B7
0x180007eae  mov     ecx, dword ptr [rbp+57h+var_78]
0x180007eb1  mov     rax, [rbp+57h+pv]
0x180007eb5  test    ecx, ecx
0x180007eb7  jz      loc_1800080BD
0x180007ebd  mov     edx, [rax+20h]
0x180007ec0  test    edx, edx
0x180007ec2  jz      loc_1800080AB
0x180007ec8  cmp     ecx, 1
0x180007ecb  jnz     loc_180008062
0x180007ed1  cmp     edx, 12h
0x180007ed4  jnz     loc_180008062
0x180007eda  mov     rsi, [rax+28h]
0x180007ede  test    rsi, rsi
0x180007ee1  jz      loc_180008062
0x180007ee7  mov     r15d, [rax+24h]
0x180007eeb  mov     ebx, r15d
0x180007eee  and     rbx, 0FFFFFFFFFFFFFFFEh
0x180007ef2  mov     rcx, rbx; cb
0x180007ef5  call    cs:__imp_CoTaskMemAlloc
0x180007efb  mov     rdi, rax
0x180007efe  test    rax, rax
0x180007f01  jz      loc_180007FF2
0x180007f07  mov     rcx, rax
0x180007f0a  lea     r8, [rbx+rax]
0x180007f0e  cmp     rax, r8
0x180007f11  jz      short loc_180007F2E
0x180007f13  nop     dword ptr [rax+00h]
0x180007f17  nop     word ptr [rax+rax+00000000h]
0x180007f20  xor     eax, eax
0x180007f22  mov     [rcx], ax
0x180007f25  add     rcx, 2
0x180007f29  cmp     rcx, r8
0x180007f2c  jnz     short loc_180007F20
0x180007f2e  mov     r8, r15; Size
0x180007f31  mov     rdx, rsi; Src
0x180007f34  mov     rcx, rdi; void *
0x180007f37  call    memcpy_0
0x180007f3c  mov     ecx, dword ptr [rbp+57h+var_78]
0x180007f3f  test    ecx, ecx
0x180007f41  jz      short loc_180007F52
0x180007f43  mov     rdx, [rbp+57h+pv]
0x180007f47  test    rdx, rdx
0x180007f4a  jz      short loc_180007F52
0x180007f4c  call    cs:__imp_DevFreeObjectProperties
0x180007f52  mov     [rbp+57h+pv], r12
0x180007f56  lea     rax, [rbp+57h+pv]
0x180007f5a  mov     [rsp+0C0h+ppv], rax
0x180007f5f  xor     r9d, r9d
0x180007f62  lea     r8, DEVPKEY_Device_MatchingDeviceId
0x180007f69  mov     rdx, [r13+8]
0x180007f6d  mov     ecx, 3
0x180007f72  call    ?GetDeviceObjectStringProperty@@YAJW4_DEV_OBJECT_TYPE@@PEBGAEBU_DEVPROPKEY@@_NPEAPEAG@Z; GetDeviceObjectStringProperty(_DEV_OBJECT_TYPE,ushort const *,_DEVPROPKEY const &,bool,ushort * *)
0x180007f77  test    eax, eax
0x180007f79  js      short loc_180007FE4
0x180007f7b  mov     [rbp+57h+var_78], r12
0x180007f7f  lea     rax, [rbp+57h+var_78]
0x180007f83  mov     [rsp+0C0h+ppv], rax; ppv
0x180007f88  lea     r9, _GUID_612118c1_b1d3_4d55_80f2_4488b55cf623; riid
0x180007f8f  xor     edx, edx; pUnkOuter
0x180007f91  mov     r8d, 1; dwClsContext
0x180007f97  lea     rcx, _GUID_6d93c83d_31c1_490e_b5f9_068a80e3d7cb; rclsid
0x180007f9e  call    cs:__imp_CoCreateInstance
0x180007fa4  test    eax, eax
0x180007fa6  js      short loc_180007FC3
0x180007fa8  mov     rcx, [rbp+57h+var_78]
0x180007fac  mov     rax, [rcx]
0x180007faf  lea     r9, [rbp+57h+var_70]
0x180007fb3  mov     r8, [rbp+57h+pv]
0x180007fb7  mov     rdx, rdi
0x180007fba  mov     rax, [rax+28h]
0x180007fbe  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007fc3  mov     rcx, [rbp+57h+pv]; pv
0x180007fc7  call    cs:__imp_CoTaskMemFree
0x180007fcd  nop
0x180007fce  mov     rcx, [rbp+57h+var_78]
0x180007fd2  test    rcx, rcx
0x180007fd5  jz      short loc_180007FE4
0x180007fd7  mov     rax, [rcx]
0x180007fda  mov     rax, [rax+10h]
0x180007fde  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007fe3  nop
0x180007fe4  mov     rcx, rdi; pv
0x180007fe7  call    cs:__imp_CoTaskMemFree
0x180007fed  jmp     loc_1800080BD
0x180007ff2  mov     rcx, [rbp+5Fh]; this
0x180007ff6  mov     r9d, 8007000Eh; char *
0x180007ffc  lea     r8, aOnecoreuapBase_0; "onecoreuap\\base\\devices\\setup\\lib\\"...
0x180008003  mov     edx, 8Bh; void *
0x180008008  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000800d  lea     rdx, WPP_GLOBAL_Control
0x180008014  mov     rcx, cs:WPP_GLOBAL_Control
0x18000801b  cmp     rcx, rdx
0x18000801e  jz      short loc_180008050
0x180008020  test    byte ptr [rcx+1Ch], 1
0x180008024  jz      short loc_180008050
0x180008026  mov     edx, 0Dh
0x18000802b  mov     dword ptr [rsp+0C0h+var_90], 8007000Eh
0x180008033  mov     [rsp+0C0h+var_98], r14
0x180008038  mov     dword ptr [rsp+0C0h+ppv], 5
0x180008040  lea     r9, DEVPKEY_Device_DriverInfPath
0x180008047  mov     rcx, [rcx+10h]
0x18000804b  call    WPP_SF__guid_dSd
0x180008050  mov     ecx, dword ptr [rbp+57h+var_78]
0x180008053  test    ecx, ecx
0x180008055  jz      short loc_1800080BD
0x180008057  mov     rdx, [rbp+57h+pv]
0x18000805b  test    rdx, rdx
0x18000805e  jnz     short loc_1800080B7
0x180008060  jmp     short loc_1800080BD
0x180008062  lea     rdx, WPP_GLOBAL_Control
0x180008069  mov     r8, cs:WPP_GLOBAL_Control
0x180008070  cmp     r8, rdx
0x180008073  jz      short loc_1800080A0
0x180008075  test    byte ptr [r8+1Ch], 1
0x18000807a  jz      short loc_1800080A0
0x18000807c  mov     [rsp+0C0h+var_98], r14
0x180008081  mov     dword ptr [rsp+0C0h+ppv], 5
0x180008089  lea     r9, DEVPKEY_Device_DriverInfPath
0x180008090  mov     rcx, [r8+10h]
0x180008094  call    WPP_SF__guid_dS
0x180008099  mov     rax, [rbp+57h+pv]
0x18000809d  mov     ecx, dword ptr [rbp+57h+var_78]
0x1800080a0  test    ecx, ecx
0x1800080a2  jz      short loc_1800080BD
0x1800080a4  test    rax, rax
0x1800080a7  jnz     short loc_1800080B4
0x1800080a9  jmp     short loc_1800080BD
0x1800080ab  test    ecx, ecx
0x1800080ad  jz      short loc_1800080BD
0x1800080af  test    rax, rax
0x1800080b2  jz      short loc_1800080BD
0x1800080b4  mov     rdx, rax
0x1800080b7  call    cs:__imp_DevFreeObjectProperties
0x1800080bd  mov     eax, [rbp+57h+var_70]
0x1800080c0  mov     rcx, [rbp+57h+var_48]
0x1800080c4  xor     rcx, rsp; StackCookie
0x1800080c7  call    __security_check_cookie
0x1800080cc  add     rsp, 88h
0x1800080d3  pop     r15
0x1800080d5  pop     r14
0x1800080d7  pop     r13
0x1800080d9  pop     r12
0x1800080db  pop     rdi
0x1800080dc  pop     rsi
0x1800080dd  pop     rbx
0x1800080de  pop     rbp
0x1800080df  retn
```
