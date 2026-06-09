# MbbNdisSmsSetConfiguration(_MBB_REQUEST_CONTEXT *,uchar *,ulong *)

- ea: `0x140017110`
- end: `0x140017220`
- name: `?MbbNdisSmsSetConfiguration@@YAHPEAU_MBB_REQUEST_CONTEXT@@PEAEPEAK@Z`
- size: `272`
- prototype: `__int64 __fastcall(struct _MBB_REQUEST_CONTEXT *, unsigned __int8 *, unsigned int *)`
- caller_count: `0`
- callee_count: `4`
- tags: `registry_config, loader_planting`

## callees

- `0x1400051ac`
- `0x140017110`
- `0x1400208bc`
- `0x1400235d8`

## pseudocode

```c
__int64 __fastcall MbbNdisSmsSetConfiguration(struct _MBB_REQUEST_CONTEXT *a1, unsigned __int8 *a2, unsigned int *a3)
{
  struct _WWAN_SET_SMS_CONFIGURATION *v4; // rcx
  unsigned __int8 *v5; // rax
  __int64 v6; // r8
  unsigned int v7; // ebx
  int v8; // r9d
  unsigned __int8 *v9; // rdx
  unsigned int v10; // r8d
  unsigned int v12; // [rsp+58h] [rbp+10h] BYREF
  struct _MBB_SET_SMS_CONFIGURATION *v13; // [rsp+60h] [rbp+18h] BYREF

  v12 = 0;
  v4 = (struct _WWAN_SET_SMS_CONFIGURATION *)(a2 + 4);
  v13 = 0;
  *a3 = 32;
  if ( a2 == (unsigned __int8 *)-4LL )
  {
    v7 = -1073741811;
  }
  else
  {
    v5 = a2 + 4;
    v6 = 21;
    do
    {
      if ( !*v5 )
        break;
      ++v5;
      --v6;
    }
    while ( v6 );
    v7 = v6 == 0 ? 0xC000000D : 0;
    a2 = (unsigned __int8 *)((21 - v6) & ((unsigned __int128)-(__int128)(unsigned __int64)v6 >> 64));
    if ( v6 )
    {
      v7 = MbbUtilWwanToMbbSmsSetConfiguration(v4, (int)a2, &v13, &v12);
      if ( !v7 )
      {
        v9 = (unsigned __int8 *)v13;
        v10 = v12;
        *((_QWORD *)a1 + 70) = v13;
        return MbbUtilSetAttributeWithParameter(a1, v9, v10);
      }
      if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      {
        v8 = 120;
LABEL_13:
        LOBYTE(a2) = 2;
        WPP_RECORDER_SF_DD(
          WPP_GLOBAL_Control->DeviceExtension,
          (_DWORD)a2,
          3,
          v8,
          (__int64)WPP_1cca14fdf6d03e1f3dcfafafd25c5fb2_Traceguids,
          *((_DWORD *)a1 + 4),
          v7);
        return v7;
      }
      return v7;
    }
  }
  if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
  {
    v8 = 119;
    goto LABEL_13;
  }
  return v7;
}

```

## disassembly

```asm
0x140017110  mov     [rsp+arg_0], rbx
0x140017115  push    rdi
0x140017116  sub     rsp, 40h
0x14001711a  mov     rdi, rcx
0x14001711d  mov     [rsp+48h+arg_8], 0
0x140017125  lea     rcx, [rdx+4]; struct _WWAN_SET_SMS_CONFIGURATION *
0x140017129  mov     [rsp+48h+arg_10], 0
0x140017132  mov     dword ptr [r8], 20h ; ' '
0x140017139  test    rcx, rcx
0x14001713c  jz      loc_1400171C8
0x140017142  mov     r9d, 15h
0x140017148  mov     rax, rcx
0x14001714b  mov     r8d, r9d
0x14001714e  cmp     byte ptr [rax], 0
0x140017151  jz      short loc_14001715C
0x140017153  inc     rax
0x140017156  sub     r8, 1
0x14001715a  jnz     short loc_14001714E
0x14001715c  mov     rax, r8
0x14001715f  neg     rax
0x140017162  mov     rax, r8
0x140017165  sbb     ebx, ebx
0x140017167  sub     r9, r8
0x14001716a  not     ebx
0x14001716c  and     ebx, 0C000000Dh
0x140017172  neg     rax
0x140017175  sbb     rdx, rdx
0x140017178  and     rdx, r9; unsigned int
0x14001717b  test    r8, r8
0x14001717e  jz      short loc_1400171CD
0x140017180  lea     r9, [rsp+48h+arg_8]; unsigned int *
0x140017185  lea     r8, [rsp+48h+arg_10]; struct _MBB_SET_SMS_CONFIGURATION **
0x14001718a  call    ?MbbUtilWwanToMbbSmsSetConfiguration@@YAJPEAU_WWAN_SET_SMS_CONFIGURATION@@KPEAPEAU_MBB_SET_SMS_CONFIGURATION@@PEAK@Z; MbbUtilWwanToMbbSmsSetConfiguration(_WWAN_SET_SMS_CONFIGURATION *,ulong,_MBB_SET_SMS_CONFIGURATION * *,ulong *)
0x14001718f  mov     ebx, eax
0x140017191  test    eax, eax
0x140017193  jz      short loc_1400171AD
0x140017195  lea     rcx, WPP_RECORDER_INITIALIZED
0x14001719c  cmp     cs:WPP_RECORDER_INITIALIZED, rcx
0x1400171a3  jz      short loc_140017212
0x1400171a5  mov     r9d, 78h ; 'x'
0x1400171ab  jmp     short loc_1400171E3
0x1400171ad  mov     rdx, [rsp+48h+arg_10]; unsigned __int8 *
0x1400171b2  mov     rcx, rdi; struct _MBB_REQUEST_CONTEXT *
0x1400171b5  mov     r8d, [rsp+48h+arg_8]; unsigned int
0x1400171ba  mov     [rdi+230h], rdx
0x1400171c1  call    ?MbbUtilSetAttributeWithParameter@@YAHPEAU_MBB_REQUEST_CONTEXT@@PEAEK@Z; MbbUtilSetAttributeWithParameter(_MBB_REQUEST_CONTEXT *,uchar *,ulong)
0x1400171c6  jmp     short loc_140017214
0x1400171c8  mov     ebx, 0C000000Dh
0x1400171cd  lea     rcx, WPP_RECORDER_INITIALIZED
0x1400171d4  cmp     cs:WPP_RECORDER_INITIALIZED, rcx
0x1400171db  jz      short loc_140017212
0x1400171dd  mov     r9d, 77h ; 'w'
0x1400171e3  mov     ecx, [rdi+10h]
0x1400171e6  lea     rax, WPP_1cca14fdf6d03e1f3dcfafafd25c5fb2_Traceguids
0x1400171ed  mov     [rsp+48h+var_18], ebx
0x1400171f1  mov     r8d, 3
0x1400171f7  mov     [rsp+48h+var_20], ecx
0x1400171fb  mov     dl, 2
0x1400171fd  mov     rcx, cs:WPP_GLOBAL_Control
0x140017204  mov     [rsp+48h+var_28], rax
0x140017209  mov     rcx, [rcx+40h]
0x14001720d  call    WPP_RECORDER_SF_DD
0x140017212  mov     eax, ebx
0x140017214  mov     rbx, [rsp+48h+arg_0]
0x140017219  add     rsp, 40h
0x14001721d  pop     rdi
0x14001721e  retn
```
