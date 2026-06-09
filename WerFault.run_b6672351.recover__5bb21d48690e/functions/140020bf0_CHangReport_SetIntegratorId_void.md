# CHangReport::SetIntegratorId(void)

- ea: `0x140020bf0`
- end: `0x140020e5b`
- name: `?SetIntegratorId@CHangReport@@AEAAJXZ`
- size: `619`
- prototype: `__int64 __fastcall(CHangReport *__hidden this)`
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x14001f2dc`

## callees

- `0x140014f14`
- `0x1400166ec`
- `0x140019c70`
- `0x140020bf0`

## import_xrefs

- `api-ms-win-core-memory-l1-1-0!UnmapViewOfFile` at `0x140020e25`
- `api-ms-win-core-memory-l1-1-0!UnmapViewOfFile` at `0x140020e25`
- `wer!WerpFreeString` at `0x140020c2f`
- `wer!WerpFreeString` at `0x140020e3b`
- `wer!WerpFreeString` at `0x140020c2f`
- `wer!WerpFreeString` at `0x140020e3b`
- `wer!WerpSetIntegratorReportId` at `0x140020c9a`
- `wer!WerpSetIntegratorReportId` at `0x140020c9a`
- `wer!WerpCreateIntegratorReportId` at `0x140020c3f`
- `wer!WerpCreateIntegratorReportId` at `0x140020c3f`

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
      WPP_SF_d(*((_QWORD *)v7 + 2), v8, WPP_6c7034e0252a3228ea586abc03935af9_Traceguids, (unsigned int)v6);
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
0x140020bf0  mov     [rsp-28h+arg_10], rbx
0x140020bf5  push    rbp
0x140020bf6  push    rsi
0x140020bf7  push    rdi
0x140020bf8  push    r14
0x140020bfa  push    r15
0x140020bfc  mov     rbp, rsp
0x140020bff  sub     rsp, 20h
0x140020c03  mov     rsi, rcx
0x140020c06  xor     r15d, r15d
0x140020c09  mov     ecx, r15d
0x140020c0c  mov     [rbp+arg_0], rcx
0x140020c10  mov     [rbp+lpBaseAddress], r15
0x140020c14  cmp     [rsi+5F78h], r15
0x140020c1b  jnz     short loc_140020C26
0x140020c1d  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x140020c22  mov     rcx, [rbp+arg_0]
0x140020c26  mov     [rbp+arg_0], r15
0x140020c2a  test    rcx, rcx
0x140020c2d  jz      short loc_140020C3B
0x140020c2f  call    cs:__imp_WerpFreeString
0x140020c36  nop     dword ptr [rax+rax+00h]
0x140020c3b  lea     rcx, [rbp+arg_0]
0x140020c3f  call    cs:__imp_WerpCreateIntegratorReportId
0x140020c46  nop     dword ptr [rax+rax+00h]
0x140020c4b  mov     ebx, eax
0x140020c4d  test    eax, eax
0x140020c4f  jns     short loc_140020C8F
0x140020c51  lea     rax, WPP_GLOBAL_Control
0x140020c58  mov     rcx, cs:WPP_GLOBAL_Control
0x140020c5f  cmp     rcx, rax
0x140020c62  jz      loc_140020E1C
0x140020c68  test    byte ptr [rcx+1Ch], 1
0x140020c6c  jz      loc_140020E1C
0x140020c72  mov     edx, 29h ; ')'
0x140020c77  mov     r9d, ebx
0x140020c7a  lea     r8, WPP_6c7034e0252a3228ea586abc03935af9_Traceguids
0x140020c81  mov     rcx, [rcx+10h]
0x140020c85  call    WPP_SF_d
0x140020c8a  jmp     loc_140020E1C
0x140020c8f  mov     rdx, [rbp+arg_0]
0x140020c93  mov     rcx, [rsi+5F78h]
0x140020c9a  call    cs:__imp_WerpSetIntegratorReportId
0x140020ca1  nop     dword ptr [rax+rax+00h]
0x140020ca6  mov     ebx, eax
0x140020ca8  test    eax, eax
0x140020caa  jns     short loc_140020CD4
0x140020cac  lea     rax, WPP_GLOBAL_Control
0x140020cb3  mov     rcx, cs:WPP_GLOBAL_Control
0x140020cba  cmp     rcx, rax
0x140020cbd  jz      loc_140020E1C
0x140020cc3  test    byte ptr [rcx+1Ch], 1
0x140020cc7  jz      loc_140020E1C
0x140020ccd  mov     edx, 2Ah ; '*'
0x140020cd2  jmp     short loc_140020C77
0x140020cd4  mov     r14d, 7FFFFFFEh
0x140020cda  mov     eax, r14d
0x140020cdd  mov     rcx, [rbp+arg_0]
0x140020ce1  mov     edi, 40h ; '@'
0x140020ce6  mov     edx, edi
0x140020ce8  lea     r8, [rsi+6000h]
0x140020cef  test    rax, rax
0x140020cf2  jz      short loc_140020D13
0x140020cf4  movzx   r9d, word ptr [rcx]
0x140020cf8  test    r9w, r9w
0x140020cfc  jz      short loc_140020D13
0x140020cfe  add     rcx, 2
0x140020d02  mov     [r8], r9w
0x140020d06  add     r8, 2
0x140020d0a  dec     rax
0x140020d0d  sub     rdx, 1
0x140020d11  jnz     short loc_140020CEF
0x140020d13  mov     rax, rdx
0x140020d16  neg     rax
0x140020d19  sbb     ebx, ebx
0x140020d1b  not     ebx
0x140020d1d  and     ebx, 8007007Ah
0x140020d23  lea     rcx, [r8-2]
0x140020d27  test    rdx, rdx
0x140020d2a  cmovnz  rcx, r8
0x140020d2e  mov     [rcx], r15w
0x140020d32  jnz     short loc_140020D5F
0x140020d34  lea     rax, WPP_GLOBAL_Control
0x140020d3b  mov     rcx, cs:WPP_GLOBAL_Control
0x140020d42  cmp     rcx, rax
0x140020d45  jz      loc_140020E1C
0x140020d4b  test    byte ptr [rcx+1Ch], 1
0x140020d4f  jz      loc_140020E1C
0x140020d55  mov     edx, 2Bh ; '+'
0x140020d5a  jmp     loc_140020C77
0x140020d5f  lea     rcx, [rsi+5D68h]; lpName
0x140020d66  lea     rdx, [rbp+lpBaseAddress]
0x140020d6a  call    ?OpenSharedMemory@@YAJPEB_WPEAV?$unique_ptr@USharedHangRepData@@U?$generic_delete@USharedHangRepData@@U?$generic_deallocate@$MP6AHPEBX@Z1?UnmapViewOfFile@@YAH0@ZPEAX@tlx@@@tlx@@@utl@@@Z
0x140020d6f  mov     ebx, eax
0x140020d71  test    eax, eax
0x140020d73  jns     short loc_140020DA0
0x140020d75  lea     rax, WPP_GLOBAL_Control
0x140020d7c  mov     rcx, cs:WPP_GLOBAL_Control
0x140020d83  cmp     rcx, rax
0x140020d86  jz      loc_140020E1C
0x140020d8c  test    byte ptr [rcx+1Ch], 1
0x140020d90  jz      loc_140020E1C
0x140020d96  mov     edx, 2Ch ; ','
0x140020d9b  jmp     loc_140020C77
0x140020da0  mov     rcx, [rbp+arg_0]
0x140020da4  mov     rdx, [rbp+lpBaseAddress]
0x140020da8  add     rdx, 6F0h
0x140020daf  test    r14, r14
0x140020db2  jz      short loc_140020DD0
0x140020db4  movzx   eax, word ptr [rcx]
0x140020db7  test    ax, ax
0x140020dba  jz      short loc_140020DD0
0x140020dbc  add     rcx, 2
0x140020dc0  mov     [rdx], ax
0x140020dc3  add     rdx, 2
0x140020dc7  dec     r14
0x140020dca  sub     rdi, 1
0x140020dce  jnz     short loc_140020DAF
0x140020dd0  mov     rax, rdi
0x140020dd3  neg     rax
0x140020dd6  sbb     ebx, ebx
0x140020dd8  not     ebx
0x140020dda  and     ebx, 8007007Ah
0x140020de0  lea     rcx, [rdx-2]
0x140020de4  test    rdi, rdi
0x140020de7  cmovnz  rcx, rdx
0x140020deb  mov     [rcx], r15w
0x140020def  jnz     short loc_140020E19
0x140020df1  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x140020df6  lea     rax, WPP_GLOBAL_Control
0x140020dfd  mov     rcx, cs:WPP_GLOBAL_Control
0x140020e04  cmp     rcx, rax
0x140020e07  jz      short loc_140020E1C
0x140020e09  test    byte ptr [rcx+1Ch], 1
0x140020e0d  jz      short loc_140020E1C
0x140020e0f  mov     edx, 2Dh ; '-'
0x140020e14  jmp     loc_140020C77
0x140020e19  mov     ebx, r15d
0x140020e1c  mov     rcx, [rbp+lpBaseAddress]; lpBaseAddress
0x140020e20  test    rcx, rcx
0x140020e23  jz      short loc_140020E32
0x140020e25  call    cs:__imp_UnmapViewOfFile
0x140020e2c  nop     dword ptr [rax+rax+00h]
0x140020e31  nop
0x140020e32  mov     rcx, [rbp+arg_0]
0x140020e36  test    rcx, rcx
0x140020e39  jz      short loc_140020E47
0x140020e3b  call    cs:__imp_WerpFreeString
0x140020e42  nop     dword ptr [rax+rax+00h]
0x140020e47  mov     eax, ebx
0x140020e49  mov     rbx, [rsp+20h+arg_10]
0x140020e4e  add     rsp, 20h
0x140020e52  pop     r15
0x140020e54  pop     r14
0x140020e56  pop     rdi
0x140020e57  pop     rsi
0x140020e58  pop     rbp
0x140020e59  retn
```
