# CConnectedUser::DeleteLocalUser(void)

- ea: `0x180017ec0`
- end: `0x180018032`
- name: `?DeleteLocalUser@CConnectedUser@@UEAAJXZ`
- size: `370`
- prototype: `__int64 __fastcall(CConnectedUser *this, __int64, int, int)`
- caller_count: `0`
- callee_count: `7`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x18000e39c`
- `0x180014430`
- `0x1800144b4`
- `0x1800144f4`
- `0x180017ec0`
- `0x180019750`
- `0x18001b010`

## import_xrefs

- `SAMLIB!SamCloseHandle` at `0x180017fee`
- `SAMLIB!SamCloseHandle` at `0x180017fee`
- `SAMLIB!SamOpenUser` at `0x180017f4d`
- `SAMLIB!SamOpenUser` at `0x180017f4d`
- `SAMLIB!SamDeleteUser` at `0x180017f9a`
- `SAMLIB!SamDeleteUser` at `0x180017f9a`

## pseudocode

```c
__int64 __fastcall CConnectedUser::DeleteLocalUser(CConnectedUser *this, __int64 a2, int a3, int a4)
{
  __int64 v5; // rax
  unsigned int v6; // ebx
  unsigned int v7; // ebx
  __int64 v8; // rax
  int v9; // ebx
  int v10; // ebx
  int v11; // ecx
  __int64 v13; // [rsp+30h] [rbp-28h] BYREF
  struct _EVENT_DATA_DESCRIPTOR v14; // [rsp+38h] [rbp-20h] BYREF

  v13 = 0;
  if ( (Microsoft_Windows_Security_IdentityStoreEnableBits & 1) != 0 )
    McGenEventWrite_EventWriteTransfer((int)this, (int)&DeleteLocalUserStart, a3, a4, &v14);
  v5 = *(_QWORD *)((char *)this + 68) - 0x4967A148B16898C6LL;
  if ( *(_QWORD *)((char *)this + 68) == 0x4967A148B16898C6LL )
    v5 = *(_QWORD *)((char *)this + 76) - 0x2085DA55D7647191LL;
  if ( v5 )
  {
    v7 = *((_DWORD *)this + 16);
    v8 = (*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)this + 11) + 24LL))(*((_QWORD *)this + 11));
    v9 = SamOpenUser(v8, 0x2000000, v7, &v13);
    if ( v9 >= 0 )
    {
      v10 = SamDeleteUser(v13);
      if ( v10 >= 0 )
      {
        v6 = 0;
        v13 = 0;
      }
      else
      {
        v6 = v10 | 0x10000000;
        if ( WPP_GLOBAL_Control != (CIdentityProfileHandler *)&WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
        {
          WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 67, WPP_08388c1448a138cd62261a2bdb1dad4c_Traceguids, v6);
        }
      }
    }
    else
    {
      if ( WPP_GLOBAL_Control != (CIdentityProfileHandler *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
      {
        WPP_SF_DD(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          66,
          WPP_08388c1448a138cd62261a2bdb1dad4c_Traceguids,
          *((unsigned int *)this + 16),
          v9);
      }
      v6 = v9 | 0x10000000;
    }
  }
  else
  {
    v6 = -2147024846;
  }
  v11 = v13;
  if ( v13 )
    SamCloseHandle();
  if ( (Microsoft_Windows_Security_IdentityStoreEnableBits & 1) != 0 )
    McGenEventWrite_EventWriteTransfer(v11, (int)&DeleteLocalUserStop, a3, a4, &v14);
  return MapErrorCodes(v6);
}

```

## disassembly

```asm
0x180017ec0  mov     r11, rsp
0x180017ec3  mov     [r11+10h], rbx
0x180017ec7  push    rdi
0x180017ec8  sub     rsp, 50h
0x180017ecc  mov     rax, cs:__security_cookie
0x180017ed3  xor     rax, rsp
0x180017ed6  mov     [rsp+58h+var_10], rax
0x180017edb  test    cs:Microsoft_Windows_Security_IdentityStoreEnableBits, 1
0x180017ee2  mov     rdi, rcx
0x180017ee5  mov     qword ptr [r11-28h], 0
0x180017eed  jz      short loc_180017F03
0x180017eef  lea     rax, [r11-20h]
0x180017ef3  lea     rdx, DeleteLocalUserStart; int
0x180017efa  mov     [r11-38h], rax
0x180017efe  call    McGenEventWrite_EventWriteTransfer
0x180017f03  mov     rax, [rdi+44h]
0x180017f07  sub     rax, qword ptr cs:xmmword_18001E7E0
0x180017f0e  jnz     short loc_180017F1B
0x180017f10  mov     rax, [rdi+4Ch]
0x180017f14  sub     rax, qword ptr cs:xmmword_18001E7E0+8
0x180017f1b  test    rax, rax
0x180017f1e  jnz     short loc_180017F2A
0x180017f20  mov     ebx, 80070032h
0x180017f25  jmp     loc_180017FE4
0x180017f2a  mov     rcx, [rdi+58h]
0x180017f2e  mov     ebx, [rdi+40h]
0x180017f31  mov     rax, [rcx]
0x180017f34  mov     rax, [rax+18h]
0x180017f38  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180017f3d  lea     r9, [rsp+58h+var_28]
0x180017f42  mov     r8d, ebx
0x180017f45  mov     edx, 2000000h
0x180017f4a  mov     rcx, rax
0x180017f4d  call    cs:__imp_SamOpenUser
0x180017f53  mov     ebx, eax
0x180017f55  test    eax, eax
0x180017f57  jns     short loc_180017F95
0x180017f59  mov     rcx, cs:WPP_GLOBAL_Control
0x180017f60  lea     rax, WPP_GLOBAL_Control
0x180017f67  cmp     rcx, rax
0x180017f6a  jz      short loc_180017F8F
0x180017f6c  test    byte ptr [rcx+1Ch], 4
0x180017f70  jz      short loc_180017F8F
0x180017f72  mov     r9d, [rdi+40h]
0x180017f76  lea     r8, WPP_08388c1448a138cd62261a2bdb1dad4c_Traceguids
0x180017f7d  mov     rcx, [rcx+10h]
0x180017f81  mov     edx, 42h ; 'B'
0x180017f86  mov     dword ptr [rsp+58h+var_38], ebx
0x180017f8a  call    WPP_SF_DD
0x180017f8f  bts     ebx, 1Ch
0x180017f93  jmp     short loc_180017FE4
0x180017f95  mov     rcx, [rsp+58h+var_28]
0x180017f9a  call    cs:__imp_SamDeleteUser
0x180017fa0  mov     ebx, eax
0x180017fa2  test    eax, eax
0x180017fa4  jns     short loc_180017FDD
0x180017fa6  bts     ebx, 1Ch
0x180017faa  mov     rcx, cs:WPP_GLOBAL_Control
0x180017fb1  lea     rax, WPP_GLOBAL_Control
0x180017fb8  cmp     rcx, rax
0x180017fbb  jz      short loc_180017FE4
0x180017fbd  test    byte ptr [rcx+1Ch], 4
0x180017fc1  jz      short loc_180017FE4
0x180017fc3  mov     rcx, [rcx+10h]
0x180017fc7  lea     r8, WPP_08388c1448a138cd62261a2bdb1dad4c_Traceguids
0x180017fce  mov     edx, 43h ; 'C'
0x180017fd3  mov     r9d, ebx
0x180017fd6  call    WPP_SF_d
0x180017fdb  jmp     short loc_180017FE4
0x180017fdd  xor     ebx, ebx
0x180017fdf  mov     [rsp+58h+var_28], rbx
0x180017fe4  mov     rcx, [rsp+58h+var_28]
0x180017fe9  test    rcx, rcx
0x180017fec  jz      short loc_180017FF4
0x180017fee  call    cs:__imp_SamCloseHandle
0x180017ff4  test    cs:Microsoft_Windows_Security_IdentityStoreEnableBits, 1
0x180017ffb  jz      short loc_180018013
0x180017ffd  lea     rax, [rsp+58h+var_20]
0x180018002  lea     rdx, DeleteLocalUserStop; int
0x180018009  mov     [rsp+58h+var_38], rax; PEVENT_DATA_DESCRIPTOR
0x18001800e  call    McGenEventWrite_EventWriteTransfer
0x180018013  mov     ecx, ebx; int
0x180018015  call    ?MapErrorCodes@@YAJJ@Z; MapErrorCodes(long)
0x18001801a  mov     rcx, [rsp+58h+var_10]
0x18001801f  xor     rcx, rsp; StackCookie
0x180018022  call    __security_check_cookie
0x180018027  mov     rbx, [rsp+58h+arg_8]
0x18001802c  add     rsp, 50h
0x180018030  pop     rdi
0x180018031  retn
```
