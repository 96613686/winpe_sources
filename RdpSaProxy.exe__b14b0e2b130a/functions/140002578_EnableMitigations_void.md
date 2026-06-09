# EnableMitigations(void)

- ea: `0x140002578`
- end: `0x140002731`
- name: `?EnableMitigations@@YAXXZ`
- size: `441`
- prototype: `void(void)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config`

## callers

- `0x140002944`

## callees

- `0x140002578`
- `0x140002738`
- `0x1400027cc`

## import_xrefs

- `KERNEL32!GetLastError` at `0x1400025c4`
- `KERNEL32!GetLastError` at `0x14000262a`
- `KERNEL32!GetLastError` at `0x140002691`
- `KERNEL32!GetLastError` at `0x1400026f8`
- `KERNEL32!GetLastError` at `0x1400025c4`
- `KERNEL32!GetLastError` at `0x14000262a`
- `KERNEL32!GetLastError` at `0x140002691`
- `KERNEL32!GetLastError` at `0x1400026f8`
- `KERNEL32!SetProcessMitigationPolicy` at `0x14000259b`
- `KERNEL32!SetProcessMitigationPolicy` at `0x140002608`
- `KERNEL32!SetProcessMitigationPolicy` at `0x14000266f`
- `KERNEL32!SetProcessMitigationPolicy` at `0x1400026d6`
- `KERNEL32!SetProcessMitigationPolicy` at `0x14000259b`
- `KERNEL32!SetProcessMitigationPolicy` at `0x140002608`
- `KERNEL32!SetProcessMitigationPolicy` at `0x14000266f`
- `KERNEL32!SetProcessMitigationPolicy` at `0x1400026d6`

## pseudocode

```c
void EnableMitigations(void)
{
  DWORD LastError; // ebx
  unsigned int CurrentThreadActivityIdPrefix; // eax
  DWORD v2; // ebx
  unsigned int v3; // eax
  DWORD v4; // ebx
  unsigned int v5; // eax
  DWORD v6; // ebx
  unsigned int v7; // eax
  int v8; // [rsp+50h] [rbp+8h] BYREF
  int v9; // [rsp+58h] [rbp+10h] BYREF
  int v10; // [rsp+60h] [rbp+18h] BYREF
  int v11; // [rsp+68h] [rbp+20h] BYREF

  v8 = 1;
  if ( !(unsigned int)SetProcessMitigationPolicy(8, &v8, 4)
    && WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    LastError = GetLastError();
    CurrentThreadActivityIdPrefix = RdpWppGetCurrentThreadActivityIdPrefix();
    WPP_SF_Dd(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      10,
      WPP_81a68826556e3429b3a0281bc52d6a65_Traceguids,
      CurrentThreadActivityIdPrefix,
      LastError);
  }
  v9 = 1;
  if ( !(unsigned int)SetProcessMitigationPolicy(2, &v9, 4)
    && WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    v2 = GetLastError();
    v3 = RdpWppGetCurrentThreadActivityIdPrefix();
    WPP_SF_Dd(*((_QWORD *)WPP_GLOBAL_Control + 2), 11, WPP_81a68826556e3429b3a0281bc52d6a65_Traceguids, v3, v2);
  }
  v10 = 1;
  if ( !(unsigned int)SetProcessMitigationPolicy(9, &v10, 4)
    && WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    v4 = GetLastError();
    v5 = RdpWppGetCurrentThreadActivityIdPrefix();
    WPP_SF_Dd(*((_QWORD *)WPP_GLOBAL_Control + 2), 12, WPP_81a68826556e3429b3a0281bc52d6a65_Traceguids, v5, v4);
  }
  v11 = 3;
  if ( !(unsigned int)SetProcessMitigationPolicy(10, &v11, 4)
    && WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    v6 = GetLastError();
    v7 = RdpWppGetCurrentThreadActivityIdPrefix();
    WPP_SF_Dd(*((_QWORD *)WPP_GLOBAL_Control + 2), 13, WPP_81a68826556e3429b3a0281bc52d6a65_Traceguids, v7, v6);
  }
}

```

## disassembly

```asm
0x140002578  push    rbx
0x14000257a  push    rbp
0x14000257b  push    r14
0x14000257d  sub     rsp, 30h
0x140002581  mov     r14d, 4
0x140002587  mov     [rsp+48h+arg_0], 1
0x14000258f  mov     r8d, r14d
0x140002592  lea     rdx, [rsp+48h+arg_0]
0x140002597  lea     ecx, [r14+4]
0x14000259b  call    cs:__imp_SetProcessMitigationPolicy
0x1400025a1  lea     rbp, WPP_GLOBAL_Control
0x1400025a8  test    eax, eax
0x1400025aa  jnz     short loc_1400025F3
0x1400025ac  mov     rax, cs:WPP_GLOBAL_Control
0x1400025b3  cmp     rax, rbp
0x1400025b6  jz      short loc_1400025F3
0x1400025b8  test    byte ptr [rax+1Ch], 1
0x1400025bc  jz      short loc_1400025F3
0x1400025be  cmp     byte ptr [rax+19h], 2
0x1400025c2  jb      short loc_1400025F3
0x1400025c4  call    cs:__imp_GetLastError
0x1400025ca  mov     ebx, eax
0x1400025cc  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x1400025d1  mov     rcx, cs:WPP_GLOBAL_Control
0x1400025d8  lea     edx, [r14+6]
0x1400025dc  mov     r9d, eax
0x1400025df  mov     [rsp+48h+var_28], ebx
0x1400025e3  lea     r8, WPP_81a68826556e3429b3a0281bc52d6a65_Traceguids
0x1400025ea  mov     rcx, [rcx+10h]
0x1400025ee  call    WPP_SF_Dd
0x1400025f3  mov     r8, r14
0x1400025f6  mov     [rsp+48h+arg_8], 1
0x1400025fe  lea     rdx, [rsp+48h+arg_8]
0x140002603  mov     ecx, 2
0x140002608  call    cs:__imp_SetProcessMitigationPolicy
0x14000260e  test    eax, eax
0x140002610  jnz     short loc_14000265A
0x140002612  mov     rax, cs:WPP_GLOBAL_Control
0x140002619  cmp     rax, rbp
0x14000261c  jz      short loc_14000265A
0x14000261e  test    byte ptr [rax+1Ch], 1
0x140002622  jz      short loc_14000265A
0x140002624  cmp     byte ptr [rax+19h], 2
0x140002628  jb      short loc_14000265A
0x14000262a  call    cs:__imp_GetLastError
0x140002630  mov     ebx, eax
0x140002632  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x140002637  mov     rcx, cs:WPP_GLOBAL_Control
0x14000263e  lea     r8, WPP_81a68826556e3429b3a0281bc52d6a65_Traceguids
0x140002645  mov     edx, 0Bh
0x14000264a  mov     [rsp+48h+var_28], ebx
0x14000264e  mov     r9d, eax
0x140002651  mov     rcx, [rcx+10h]
0x140002655  call    WPP_SF_Dd
0x14000265a  mov     r8, r14
0x14000265d  mov     [rsp+48h+arg_10], 1
0x140002665  lea     rdx, [rsp+48h+arg_10]
0x14000266a  mov     ecx, 9
0x14000266f  call    cs:__imp_SetProcessMitigationPolicy
0x140002675  test    eax, eax
0x140002677  jnz     short loc_1400026C1
0x140002679  mov     rax, cs:WPP_GLOBAL_Control
0x140002680  cmp     rax, rbp
0x140002683  jz      short loc_1400026C1
0x140002685  test    byte ptr [rax+1Ch], 1
0x140002689  jz      short loc_1400026C1
0x14000268b  cmp     byte ptr [rax+19h], 2
0x14000268f  jb      short loc_1400026C1
0x140002691  call    cs:__imp_GetLastError
0x140002697  mov     ebx, eax
0x140002699  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x14000269e  mov     rcx, cs:WPP_GLOBAL_Control
0x1400026a5  lea     r8, WPP_81a68826556e3429b3a0281bc52d6a65_Traceguids
0x1400026ac  mov     edx, 0Ch
0x1400026b1  mov     [rsp+48h+var_28], ebx
0x1400026b5  mov     r9d, eax
0x1400026b8  mov     rcx, [rcx+10h]
0x1400026bc  call    WPP_SF_Dd
0x1400026c1  mov     r8, r14
0x1400026c4  mov     [rsp+48h+arg_18], 3
0x1400026cc  lea     rdx, [rsp+48h+arg_18]
0x1400026d1  mov     ecx, 0Ah
0x1400026d6  call    cs:__imp_SetProcessMitigationPolicy
0x1400026dc  test    eax, eax
0x1400026de  jnz     short loc_140002728
0x1400026e0  mov     rax, cs:WPP_GLOBAL_Control
0x1400026e7  cmp     rax, rbp
0x1400026ea  jz      short loc_140002728
0x1400026ec  test    byte ptr [rax+1Ch], 1
0x1400026f0  jz      short loc_140002728
0x1400026f2  cmp     byte ptr [rax+19h], 2
0x1400026f6  jb      short loc_140002728
0x1400026f8  call    cs:__imp_GetLastError
0x1400026fe  mov     ebx, eax
0x140002700  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x140002705  mov     rcx, cs:WPP_GLOBAL_Control
0x14000270c  lea     r8, WPP_81a68826556e3429b3a0281bc52d6a65_Traceguids
0x140002713  mov     edx, 0Dh
0x140002718  mov     [rsp+48h+var_28], ebx
0x14000271c  mov     r9d, eax
0x14000271f  mov     rcx, [rcx+10h]
0x140002723  call    WPP_SF_Dd
0x140002728  add     rsp, 30h
0x14000272c  pop     r14
0x14000272e  pop     rbp
0x14000272f  pop     rbx
0x140002730  retn
```
