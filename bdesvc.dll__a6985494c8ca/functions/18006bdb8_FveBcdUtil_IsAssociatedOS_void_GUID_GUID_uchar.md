# FveBcdUtil::IsAssociatedOS(void *,_GUID *,_GUID *,uchar *)

- ea: `0x18006bdb8`
- end: `0x18006bebb`
- name: `?IsAssociatedOS@FveBcdUtil@@SAJPEAXPEAU_GUID@@1PEAE@Z`
- size: `259`
- prototype: `__int64 __fastcall(void *, struct _GUID *, struct _GUID *, unsigned __int8 *)`
- caller_count: `1`
- callee_count: `4`
- tags: `file_ops`

## callers

- `0x18006ad70`

## callees

- `0x18001b890`
- `0x180034610`
- `0x18006b0b8`
- `0x18006bdb8`

## import_xrefs

- `bcd!BcdOpenObject` at `0x18006bded`
- `bcd!BcdOpenObject` at `0x18006bded`
- `bcd!BcdCloseObject` at `0x18006be9c`
- `bcd!BcdCloseObject` at `0x18007d30c`
- `bcd!BcdCloseObject` at `0x18006be9c`
- `bcd!BcdCloseObject` at `0x18007d30c`

## pseudocode

```c
__int64 __fastcall FveBcdUtil::IsAssociatedOS(void *a1, struct _GUID *a2, struct _GUID *a3, unsigned __int8 *a4)
{
  int v6; // eax
  int v7; // ebx
  int BcdElementData; // eax
  unsigned int i; // eax
  _QWORD *v10; // r8
  __int64 v11; // rdx
  void *Block; // [rsp+28h] [rbp-20h] BYREF
  void *v14; // [rsp+30h] [rbp-18h] BYREF
  unsigned int v15; // [rsp+68h] [rbp+20h] BYREF

  v14 = 0;
  Block = 0;
  v15 = 0;
  *a4 = 0;
  v6 = BcdOpenObject(a1, a2, &v14);
  v7 = FromNtStatus(v6);
  if ( v7 >= 0 )
  {
    BcdElementData = FveBcdUtil::GetBcdElementData(v14, 0x14000008u, &Block, &v15);
    v7 = BcdElementData;
    if ( BcdElementData >= 0 )
    {
      if ( (v15 & 0xF) != 0 )
      {
        v7 = -2147024809;
      }
      else
      {
        for ( i = 0; i < v15 >> 4; ++i )
        {
          v10 = (char *)Block + 16 * i;
          v11 = *(_QWORD *)&a3->Data1 - *v10;
          if ( *(_QWORD *)&a3->Data1 == *v10 )
            v11 = *(_QWORD *)a3->Data4 - v10[1];
          if ( !v11 )
          {
            *a4 = 1;
            break;
          }
        }
      }
    }
    else if ( BcdElementData == -2147023728 )
    {
      v7 = 0;
    }
  }
  if ( Block )
    operator delete(Block);
  if ( v14 )
    BcdCloseObject(v14);
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x18006bdb8  mov     rax, rsp
0x18006bdbb  mov     [rax+8], rbx
0x18006bdbf  mov     [rax+10h], rsi
0x18006bdc3  push    rdi
0x18006bdc4  sub     rsp, 40h
0x18006bdc8  mov     rdi, r9
0x18006bdcb  mov     rsi, r8
0x18006bdce  mov     qword ptr [rax-18h], 0
0x18006bdd6  mov     qword ptr [rax-20h], 0
0x18006bdde  mov     dword ptr [rax+20h], 0
0x18006bde5  mov     byte ptr [r9], 0
0x18006bde9  lea     r8, [rax-18h]
0x18006bded  call    cs:__imp_BcdOpenObject
0x18006bdf4  nop     dword ptr [rax+rax+00h]
0x18006bdf9  mov     ecx, eax; int
0x18006bdfb  call    ?FromNtStatus@@YAJJ@Z; FromNtStatus(long)
0x18006be00  mov     ebx, eax
0x18006be02  mov     [rsp+48h+var_28], eax
0x18006be06  test    eax, eax
0x18006be08  js      short loc_18006BE83
0x18006be0a  lea     r9, [rsp+48h+arg_18]; unsigned int *
0x18006be0f  lea     r8, [rsp+48h+Block]; void **
0x18006be14  mov     edx, 14000008h; unsigned int
0x18006be19  mov     rcx, [rsp+48h+var_18]; void *
0x18006be1e  call    ?GetBcdElementData@FveBcdUtil@@SAJPEAXKPEAPEAXPEAK@Z; FveBcdUtil::GetBcdElementData(void *,ulong,void * *,ulong *)
0x18006be23  mov     ebx, eax
0x18006be25  mov     [rsp+48h+var_28], eax
0x18006be29  test    eax, eax
0x18006be2b  jns     short loc_18006BE3C
0x18006be2d  cmp     eax, 80070490h
0x18006be32  jnz     short loc_18006BE83
0x18006be34  xor     ebx, ebx
0x18006be36  mov     [rsp+48h+var_28], ebx
0x18006be3a  jmp     short loc_18006BE83
0x18006be3c  mov     ecx, [rsp+48h+arg_18]
0x18006be40  test    cl, 0Fh
0x18006be43  jz      short loc_18006BE4C
0x18006be45  mov     ebx, 80070057h
0x18006be4a  jmp     short loc_18006BE36
0x18006be4c  shr     ecx, 4
0x18006be4f  xor     eax, eax
0x18006be51  mov     [rsp+48h+var_24], eax
0x18006be55  cmp     eax, ecx
0x18006be57  jnb     short loc_18006BE83
0x18006be59  mov     r8d, eax
0x18006be5c  shl     r8, 4
0x18006be60  add     r8, [rsp+48h+Block]
0x18006be65  mov     rdx, [rsi]
0x18006be68  sub     rdx, [r8]
0x18006be6b  jnz     short loc_18006BE75
0x18006be6d  mov     rdx, [rsi+8]
0x18006be71  sub     rdx, [r8+8]
0x18006be75  test    rdx, rdx
0x18006be78  jnz     short loc_18006BE7F
0x18006be7a  mov     byte ptr [rdi], 1
0x18006be7d  jmp     short loc_18006BE83
0x18006be7f  inc     eax
0x18006be81  jmp     short loc_18006BE51
0x18006be83  mov     rcx, [rsp+48h+Block]; Block
0x18006be88  test    rcx, rcx
0x18006be8b  jz      short loc_18006BE92
0x18006be8d  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18006be92  mov     rcx, [rsp+48h+var_18]
0x18006be97  test    rcx, rcx
0x18006be9a  jz      short loc_18006BEA8
0x18006be9c  call    cs:__imp_BcdCloseObject
0x18006bea3  nop     dword ptr [rax+rax+00h]
0x18006bea8  mov     eax, ebx
0x18006beaa  mov     rbx, [rsp+48h+arg_0]
0x18006beaf  mov     rsi, [rsp+48h+arg_8]
0x18006beb4  add     rsp, 40h
0x18006beb8  pop     rdi
0x18006beb9  retn
0x18007d2eb  push    rbp
0x18007d2ed  sub     rsp, 20h
0x18007d2f1  mov     rbp, rdx
0x18007d2f4  mov     rcx, [rbp+28h]; Block
0x18007d2f8  test    rcx, rcx
0x18007d2fb  jz      short loc_18007D303
0x18007d2fd  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18007d302  nop
0x18007d303  mov     rcx, [rbp+30h]
0x18007d307  test    rcx, rcx
0x18007d30a  jz      short loc_18007D319
0x18007d30c  call    cs:__imp_BcdCloseObject
0x18007d313  nop     dword ptr [rax+rax+00h]
0x18007d318  nop
0x18007d319  add     rsp, 20h
0x18007d31d  pop     rbp
0x18007d31e  retn
```
