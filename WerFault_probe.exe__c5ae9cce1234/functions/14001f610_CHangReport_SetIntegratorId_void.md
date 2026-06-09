# CHangReport::SetIntegratorId(void)

- ea: `0x14001f610`
- end: `0x14001f85c`
- name: `?SetIntegratorId@CHangReport@@AEAAJXZ`
- size: `588`
- prototype: `__int64 __fastcall(CHangReport *__hidden this)`
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x14001dd84`

## callees

- `0x140014474`
- `0x140015b40`
- `0x140018dbc`
- `0x14001f610`

## import_xrefs

- `api-ms-win-core-memory-l1-1-0!UnmapViewOfFile` at `0x14001f833`
- `api-ms-win-core-memory-l1-1-0!UnmapViewOfFile` at `0x14001f833`
- `wer!WerpFreeString` at `0x14001f64f`
- `wer!WerpFreeString` at `0x14001f843`
- `wer!WerpFreeString` at `0x14001f64f`
- `wer!WerpFreeString` at `0x14001f843`
- `wer!WerpSetIntegratorReportId` at `0x14001f6ae`
- `wer!WerpSetIntegratorReportId` at `0x14001f6ae`
- `wer!WerpCreateIntegratorReportId` at `0x14001f659`
- `wer!WerpCreateIntegratorReportId` at `0x14001f659`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall CHangReport::SetIntegratorId(CHangReport *this, __int64 a2, __int64 a3, __int64 a4)
{
  _WORD *v5; // rcx
  signed int v6; // ebx
  CUserModeHangReport *v7; // rcx
  __int64 v8; // rdx
  __int64 v9; // r14
  __int64 v10; // rax
  __int16 *v11; // rcx
  __int64 v12; // rdi
  __int64 v13; // rdx
  _WORD *v14; // r8
  __int16 v15; // r9
  _WORD *v16; // rcx
  __int64 v17; // r8
  __int64 v18; // r9
  __int16 *v19; // rcx
  _WORD *v20; // rdx
  __int16 v21; // ax
  _WORD *v22; // rcx
  _WORD *v24; // [rsp+50h] [rbp+30h] BYREF
  LPCVOID lpBaseAddress; // [rsp+58h] [rbp+38h] BYREF

  v5 = 0;
  v24 = 0;
  lpBaseAddress = 0;
  if ( !*((_QWORD *)this + 3055) )
  {
    MicrosoftTelemetryAssertTriggeredNoArgs(0, a2, a3, a4);
    v5 = v24;
  }
  v24 = 0;
  if ( v5 )
    WerpFreeString();
  v6 = WerpCreateIntegratorReportId(&v24);
  if ( v6 >= 0 )
  {
    v6 = WerpSetIntegratorReportId(*((_QWORD *)this + 3055), v24);
    if ( v6 >= 0 )
    {
      v9 = 2147483646;
      v10 = 2147483646;
      v11 = v24;
      v12 = 64;
      v13 = 64;
      v14 = (_WORD *)((char *)this + 24576);
      do
      {
        if ( !v10 )
          break;
        v15 = *v11;
        if ( !*v11 )
          break;
        ++v11;
        *v14++ = v15;
        --v10;
        --v13;
      }
      while ( v13 );
      v6 = v13 == 0 ? 0x8007007A : 0;
      v16 = v14 - 1;
      if ( v13 )
        v16 = v14;
      *v16 = 0;
      if ( v13 )
      {
        v6 = OpenSharedMemory((LPCWSTR)this + 11956, &lpBaseAddress);
        if ( v6 >= 0 )
        {
          v19 = v24;
          v20 = (char *)lpBaseAddress + 1776;
          do
          {
            if ( !v9 )
              break;
            v21 = *v19;
            if ( !*v19 )
              break;
            ++v19;
            *v20++ = v21;
            --v9;
            --v12;
          }
          while ( v12 );
          v6 = v12 == 0 ? 0x8007007A : 0;
          v22 = v20 - 1;
          if ( v12 )
            v22 = v20;
          *v22 = 0;
          if ( v12 )
          {
            v6 = 0;
          }
          else
          {
            MicrosoftTelemetryAssertTriggeredNoArgs(v22, v20, v17, v18);
            v7 = WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control != (CUserModeHangReport *)&WPP_GLOBAL_Control
              && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
            {
              v8 = 45;
              goto LABEL_9;
            }
          }
        }
        else
        {
          v7 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control != (CUserModeHangReport *)&WPP_GLOBAL_Control
            && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
          {
            v8 = 44;
            goto LABEL_9;
          }
        }
      }
      else
      {
        v7 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != (CUserModeHangReport *)&WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        {
          v8 = 43;
          goto LABEL_9;
        }
      }
    }
    else
    {
      v7 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (CUserModeHangReport *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      {
        v8 = 42;
        goto LABEL_9;
      }
    }
  }
  else
  {
    v7 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (CUserModeHangReport *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      v8 = 41;
LABEL_9:
      WPP_SF_d(*((_QWORD *)v7 + 2), v8, &WPP_6c7034e0252a3228ea586abc03935af9_Traceguids, (unsigned int)v6);
    }
  }
  if ( lpBaseAddress )
    UnmapViewOfFile(lpBaseAddress);
  if ( v24 )
    WerpFreeString();
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x14001f610  mov     [rsp-28h+arg_10], rbx
0x14001f615  push    rbp
0x14001f616  push    rsi
0x14001f617  push    rdi
0x14001f618  push    r14
0x14001f61a  push    r15
0x14001f61c  mov     rbp, rsp
0x14001f61f  sub     rsp, 20h
0x14001f623  mov     rsi, rcx
0x14001f626  xor     r15d, r15d
0x14001f629  mov     ecx, r15d
0x14001f62c  mov     [rbp+arg_0], rcx
0x14001f630  mov     [rbp+lpBaseAddress], r15
0x14001f634  cmp     [rsi+5F78h], r15
0x14001f63b  jnz     short loc_14001F646
0x14001f63d  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x14001f642  mov     rcx, [rbp+arg_0]
0x14001f646  mov     [rbp+arg_0], r15
0x14001f64a  test    rcx, rcx
0x14001f64d  jz      short loc_14001F655
0x14001f64f  call    cs:__imp_WerpFreeString
0x14001f655  lea     rcx, [rbp+arg_0]
0x14001f659  call    cs:__imp_WerpCreateIntegratorReportId
0x14001f65f  mov     ebx, eax
0x14001f661  test    eax, eax
0x14001f663  jns     short loc_14001F6A3
0x14001f665  lea     rax, WPP_GLOBAL_Control
0x14001f66c  mov     rcx, cs:WPP_GLOBAL_Control
0x14001f673  cmp     rcx, rax
0x14001f676  jz      loc_14001F82A
0x14001f67c  test    byte ptr [rcx+1Ch], 1
0x14001f680  jz      loc_14001F82A
0x14001f686  mov     edx, 29h ; ')'
0x14001f68b  mov     r9d, ebx
0x14001f68e  lea     r8, WPP_6c7034e0252a3228ea586abc03935af9_Traceguids
0x14001f695  mov     rcx, [rcx+10h]
0x14001f699  call    WPP_SF_d
0x14001f69e  jmp     loc_14001F82A
0x14001f6a3  mov     rdx, [rbp+arg_0]
0x14001f6a7  mov     rcx, [rsi+5F78h]
0x14001f6ae  call    cs:__imp_WerpSetIntegratorReportId
0x14001f6b4  mov     ebx, eax
0x14001f6b6  test    eax, eax
0x14001f6b8  jns     short loc_14001F6E2
0x14001f6ba  lea     rax, WPP_GLOBAL_Control
0x14001f6c1  mov     rcx, cs:WPP_GLOBAL_Control
0x14001f6c8  cmp     rcx, rax
0x14001f6cb  jz      loc_14001F82A
0x14001f6d1  test    byte ptr [rcx+1Ch], 1
0x14001f6d5  jz      loc_14001F82A
0x14001f6db  mov     edx, 2Ah ; '*'
0x14001f6e0  jmp     short loc_14001F68B
0x14001f6e2  mov     r14d, 7FFFFFFEh
0x14001f6e8  mov     eax, r14d
0x14001f6eb  mov     rcx, [rbp+arg_0]
0x14001f6ef  mov     edi, 40h ; '@'
0x14001f6f4  mov     edx, edi
0x14001f6f6  lea     r8, [rsi+6000h]
0x14001f6fd  test    rax, rax
0x14001f700  jz      short loc_14001F721
0x14001f702  movzx   r9d, word ptr [rcx]
0x14001f706  test    r9w, r9w
0x14001f70a  jz      short loc_14001F721
0x14001f70c  add     rcx, 2
0x14001f710  mov     [r8], r9w
0x14001f714  add     r8, 2
0x14001f718  dec     rax
0x14001f71b  sub     rdx, 1
0x14001f71f  jnz     short loc_14001F6FD
0x14001f721  mov     rax, rdx
0x14001f724  neg     rax
0x14001f727  sbb     ebx, ebx
0x14001f729  not     ebx
0x14001f72b  and     ebx, 8007007Ah
0x14001f731  lea     rcx, [r8-2]
0x14001f735  test    rdx, rdx
0x14001f738  cmovnz  rcx, r8
0x14001f73c  mov     [rcx], r15w
0x14001f740  jnz     short loc_14001F76D
0x14001f742  lea     rax, WPP_GLOBAL_Control
0x14001f749  mov     rcx, cs:WPP_GLOBAL_Control
0x14001f750  cmp     rcx, rax
0x14001f753  jz      loc_14001F82A
0x14001f759  test    byte ptr [rcx+1Ch], 1
0x14001f75d  jz      loc_14001F82A
0x14001f763  mov     edx, 2Bh ; '+'
0x14001f768  jmp     loc_14001F68B
0x14001f76d  lea     rcx, [rsi+5D68h]; lpName
0x14001f774  lea     rdx, [rbp+lpBaseAddress]
0x14001f778  call    ?OpenSharedMemory@@YAJPEB_WPEAV?$unique_ptr@USharedHangRepData@@U?$generic_delete@USharedHangRepData@@U?$generic_deallocate@$MP6AHPEBX@Z1?UnmapViewOfFile@@YAH0@ZPEAX@tlx@@@tlx@@@utl@@@Z
0x14001f77d  mov     ebx, eax
0x14001f77f  test    eax, eax
0x14001f781  jns     short loc_14001F7AE
0x14001f783  lea     rax, WPP_GLOBAL_Control
0x14001f78a  mov     rcx, cs:WPP_GLOBAL_Control
0x14001f791  cmp     rcx, rax
0x14001f794  jz      loc_14001F82A
0x14001f79a  test    byte ptr [rcx+1Ch], 1
0x14001f79e  jz      loc_14001F82A
0x14001f7a4  mov     edx, 2Ch ; ','
0x14001f7a9  jmp     loc_14001F68B
0x14001f7ae  mov     rcx, [rbp+arg_0]
0x14001f7b2  mov     rdx, [rbp+lpBaseAddress]
0x14001f7b6  add     rdx, 6F0h
0x14001f7bd  test    r14, r14
0x14001f7c0  jz      short loc_14001F7DE
0x14001f7c2  movzx   eax, word ptr [rcx]
0x14001f7c5  test    ax, ax
0x14001f7c8  jz      short loc_14001F7DE
0x14001f7ca  add     rcx, 2
0x14001f7ce  mov     [rdx], ax
0x14001f7d1  add     rdx, 2
0x14001f7d5  dec     r14
0x14001f7d8  sub     rdi, 1
0x14001f7dc  jnz     short loc_14001F7BD
0x14001f7de  mov     rax, rdi
0x14001f7e1  neg     rax
0x14001f7e4  sbb     ebx, ebx
0x14001f7e6  not     ebx
0x14001f7e8  and     ebx, 8007007Ah
0x14001f7ee  lea     rcx, [rdx-2]
0x14001f7f2  test    rdi, rdi
0x14001f7f5  cmovnz  rcx, rdx
0x14001f7f9  mov     [rcx], r15w
0x14001f7fd  jnz     short loc_14001F827
0x14001f7ff  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x14001f804  lea     rax, WPP_GLOBAL_Control
0x14001f80b  mov     rcx, cs:WPP_GLOBAL_Control
0x14001f812  cmp     rcx, rax
0x14001f815  jz      short loc_14001F82A
0x14001f817  test    byte ptr [rcx+1Ch], 1
0x14001f81b  jz      short loc_14001F82A
0x14001f81d  mov     edx, 2Dh ; '-'
0x14001f822  jmp     loc_14001F68B
0x14001f827  mov     ebx, r15d
0x14001f82a  mov     rcx, [rbp+lpBaseAddress]; lpBaseAddress
0x14001f82e  test    rcx, rcx
0x14001f831  jz      short loc_14001F83A
0x14001f833  call    cs:__imp_UnmapViewOfFile
0x14001f839  nop
0x14001f83a  mov     rcx, [rbp+arg_0]
0x14001f83e  test    rcx, rcx
0x14001f841  jz      short loc_14001F849
0x14001f843  call    cs:__imp_WerpFreeString
0x14001f849  mov     eax, ebx
0x14001f84b  mov     rbx, [rsp+20h+arg_10]
0x14001f850  add     rsp, 20h
0x14001f854  pop     r15
0x14001f856  pop     r14
0x14001f858  pop     rdi
0x14001f859  pop     rsi
0x14001f85a  pop     rbp
0x14001f85b  retn
```
