# ValidateProperties(HNETSETUP__ *,_NETSETUP_OBJECT_ID const *,_NETSETUPPROPERTY const *,ulong,_NETSETUP_OBJECT_TYPE,PropertyAccessType)

- ea: `0x180002220`
- end: `0x180002317`
- name: `?ValidateProperties@@YAXPEAUHNETSETUP__@@PEBU_NETSETUP_OBJECT_ID@@PEBU_NETSETUPPROPERTY@@KW4_NETSETUP_OBJECT_TYPE@@W4PropertyAccessType@@@Z`
- size: `247`
- prototype: `void __fastcall(NetSetup2::Exception *, struct HNETSETUP__ *, __int64, unsigned int, int)`
- caller_count: `2`
- callee_count: `5`
- tags: `installer_update`

## callers

- `0x18000db4c`
- `0x18000dcc8`

## callees

- `0x180002220`
- `0x180002320`
- `0x180006608`
- `0x18000895c`
- `0x18000fc74`

## pseudocode

```c
void __fastcall ValidateProperties(
        NetSetup2::Exception *a1,
        struct HNETSETUP__ *a2,
        __int64 a3,
        unsigned int a4,
        int a5)
{
  __int64 v9; // rsi
  __int64 v10; // rbx
  unsigned int i; // edx
  __int64 v12; // r8
  __int64 v13; // rax
  __int64 v14; // rcx
  _BYTE pExceptionObject[264]; // [rsp+30h] [rbp-108h] BYREF

  v9 = 0;
  while ( (unsigned int)v9 < a4 )
  {
    v10 = a3 + 48 * v9;
    ValidateProperty(a1, a2, (struct _NETSETUP_OBJECT_ID *)v10, a5);
    v9 = (unsigned int)(v9 + 1);
    for ( i = v9; i < a4; ++i )
    {
      v12 = *(unsigned int *)(v10 + 16);
      v13 = 48LL * i;
      if ( (_DWORD)v12 == *(_DWORD *)(v13 + a3 + 16) )
      {
        v14 = *(_QWORD *)v10 - *(_QWORD *)(v13 + a3);
        if ( *(_QWORD *)v10 == *(_QWORD *)(v13 + a3) )
          v14 = *(_QWORD *)(v10 + 8) - *(_QWORD *)(v13 + a3 + 8);
        if ( !v14 && *(_QWORD *)(v10 + 24) == *(_QWORD *)(v13 + a3 + 24) )
        {
          if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
            WPP_SF__guid_D(*((_QWORD *)WPP_GLOBAL_Control + 2), 55, v12, v10, *(_DWORD *)(v10 + 16));
          HResultException::HResultException((HResultException *)pExceptionObject, -2147024809);
          throw (HResultException *)pExceptionObject;
        }
      }
    }
  }
}

```

## disassembly

```asm
0x180002220  push    rbx
0x180002222  push    rbp
0x180002223  push    rsi
0x180002224  push    rdi
0x180002225  push    r12
0x180002227  push    r14
0x180002229  push    r15
0x18000222b  sub     rsp, 100h
0x180002232  mov     r12d, [rsp+138h+arg_28]
0x18000223a  mov     ebp, r9d
0x18000223d  mov     rdi, r8
0x180002240  mov     r14, rdx
0x180002243  mov     r15, rcx
0x180002246  xor     esi, esi
0x180002248  cmp     esi, ebp
0x18000224a  jb      short loc_18000225E
0x18000224c  add     rsp, 100h
0x180002253  pop     r15
0x180002255  pop     r14
0x180002257  pop     r12
0x180002259  pop     rdi
0x18000225a  pop     rsi
0x18000225b  pop     rbp
0x18000225c  pop     rbx
0x18000225d  retn
0x18000225e  mov     r9d, [rsp+138h+arg_20]
0x180002266  lea     rbx, [rsi+rsi*2]
0x18000226a  shl     rbx, 4
0x18000226e  mov     rdx, r14
0x180002271  add     rbx, rdi
0x180002274  mov     [rsp+138h+var_118], r12d
0x180002279  mov     r8, rbx
0x18000227c  mov     rcx, r15
0x18000227f  call    ValidateProperty
0x180002284  inc     esi
0x180002286  mov     edx, esi
0x180002288  cmp     edx, ebp
0x18000228a  jnb     short loc_180002248
0x18000228c  mov     r8d, [rbx+10h]
0x180002290  mov     eax, edx
0x180002292  lea     rax, [rax+rax*2]
0x180002296  shl     rax, 4
0x18000229a  cmp     r8d, [rax+rdi+10h]
0x18000229f  jz      short loc_1800022A5
0x1800022a1  inc     edx
0x1800022a3  jmp     short loc_180002288
0x1800022a5  mov     rcx, [rbx]
0x1800022a8  sub     rcx, [rax+rdi]
0x1800022ac  jnz     short loc_1800022B7
0x1800022ae  mov     rcx, [rbx+8]
0x1800022b2  sub     rcx, [rax+rdi+8]
0x1800022b7  test    rcx, rcx
0x1800022ba  jnz     short loc_1800022A1
0x1800022bc  mov     rax, [rax+rdi+18h]
0x1800022c1  cmp     [rbx+18h], rax
0x1800022c5  jnz     short loc_1800022A1
0x1800022c7  mov     rcx, cs:WPP_GLOBAL_Control
0x1800022ce  lea     rax, WPP_GLOBAL_Control
0x1800022d5  cmp     rcx, rax
0x1800022d8  jz      short loc_1800022F6
0x1800022da  cmp     byte ptr [rcx+19h], 2
0x1800022de  jb      short loc_1800022F6
0x1800022e0  mov     rcx, [rcx+10h]
0x1800022e4  mov     edx, 37h ; '7'
0x1800022e9  mov     r9, rbx
0x1800022ec  mov     [rsp+138h+var_118], r8d
0x1800022f1  call    WPP_SF__guid_D
0x1800022f6  mov     edx, 80070057h; int
0x1800022fb  lea     rcx, [rsp+138h+pExceptionObject]; this
0x180002300  call    ??0HResultException@@QEAA@J@Z; HResultException::HResultException(long)
0x180002305  lea     rdx, _TI3?AVHResultException@@; pThrowInfo
0x18000230c  lea     rcx, [rsp+138h+pExceptionObject]; pExceptionObject
0x180002311  call    _CxxThrowException_0
```
