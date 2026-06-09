# MbbUtilDeviceServiceCommand(_MBB_REQUEST_CONTEXT *,uchar *,ulong *)

- ea: `0x14001e7b8`
- end: `0x14001ea0f`
- name: `?MbbUtilDeviceServiceCommand@@YAHPEAU_MBB_REQUEST_CONTEXT@@PEAEPEAK@Z`
- size: `599`
- prototype: `__int64 __fastcall(struct _MBB_REQUEST_CONTEXT *, unsigned __int8 *, __int64)`
- caller_count: `1`
- callee_count: `6`
- tags: `loader_planting, service_task, installer_update, broker_com_uri`

## callers

- `0x140010db0`

## callees

- `0x1400051ac`
- `0x140005644`
- `0x1400182ec`
- `0x14001e7b8`
- `0x1400206cc`
- `0x140020988`

## pseudocode

```c
__int64 __fastcall MbbUtilDeviceServiceCommand(struct _MBB_REQUEST_CONTEXT *a1, unsigned __int8 *a2, _DWORD *a3)
{
  unsigned __int64 v4; // rdx
  _DWORD *v5; // r14
  unsigned int v7; // ebx
  __int64 v8; // r10
  bool v9; // zf
  __int128 v10; // xmm0
  int v11; // edx
  int v12; // r9d
  unsigned int v13; // eax
  int v14; // edx
  int v16; // [rsp+28h] [rbp-70h]
  char v17; // [rsp+30h] [rbp-68h]
  char v18; // [rsp+30h] [rbp-68h]
  __int128 v19; // [rsp+50h] [rbp-48h] BYREF
  int v20; // [rsp+60h] [rbp-38h]

  v19 = 0u;
  v4 = (unsigned int)*a3;
  v5 = a3;
  if ( (unsigned int)v4 >= 0x1C )
  {
    if ( *a2 == 0x80 && *((_WORD *)a2 + 1) >= 0x1Cu && (LODWORD(a3) = 1, a2[1]) )
    {
      v8 = *((unsigned int *)a2 + 6);
      if ( v8 + 28 <= v4 )
      {
        v9 = *((_QWORD *)a1 + 53) == 0;
        v10 = *(_OWORD *)(a2 + 4);
        v20 = *((_DWORD *)a2 + 5);
        v19 = v10;
        if ( v9 && !*((_BYTE *)a1 + 576) || !*((_BYTE *)a1 + 452) )
          LODWORD(a3) = 0;
        v7 = MbbUtilSetupCommandMessage((__int64)a1, (__int64)&v19, (int)a3, (__int64)(a2 + 28), v8);
        if ( v7 )
        {
          if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
            return v7;
          v12 = 39;
          v18 = v7;
          v16 = *((_DWORD *)a1 + 4);
        }
        else
        {
          *v5 += *((_DWORD *)a2 + 6);
          v13 = MbbUtilSendMessageFragmentsAndLog(a1);
          v7 = v13;
          if ( !v13 || v13 == 259 || WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
            return v7;
          v12 = 40;
          v18 = v13;
          v16 = *((_DWORD *)a1 + 4);
        }
        LOBYTE(v11) = 2;
        WPP_RECORDER_SF_DD(
          WPP_GLOBAL_Control->DeviceExtension,
          v11,
          3,
          v12,
          (__int64)WPP_dce8bfe23d3239629ed9d053a5b71e5e_Traceguids,
          v16,
          v18);
        return v7;
      }
      if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      {
        v17 = v4;
        LOBYTE(v4) = 2;
        WPP_RECORDER_SF_Ddd(
          WPP_GLOBAL_Control->DeviceExtension,
          v4,
          3,
          38,
          (__int64)WPP_dce8bfe23d3239629ed9d053a5b71e5e_Traceguids,
          *((_DWORD *)a1 + 4),
          v17,
          28);
      }
      v7 = -1073676268;
      *v5 = *((_DWORD *)a2 + 6) + 28;
    }
    else
    {
      if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      {
        v14 = *a2;
        LOBYTE(v14) = 2;
        WPP_RECORDER_SF_DDdd(
          WPP_GLOBAL_Control->DeviceExtension,
          v14,
          (_DWORD)a3,
          37,
          (__int64)WPP_dce8bfe23d3239629ed9d053a5b71e5e_Traceguids,
          *((_DWORD *)a1 + 4),
          *a2,
          *((_WORD *)a2 + 1),
          a2[1]);
      }
      return (unsigned int)-1073676267;
    }
  }
  else
  {
    if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      LOBYTE(v4) = 2;
      WPP_RECORDER_SF_Ddd(
        WPP_GLOBAL_Control->DeviceExtension,
        v4,
        3,
        36,
        (__int64)WPP_dce8bfe23d3239629ed9d053a5b71e5e_Traceguids,
        *((_DWORD *)a1 + 4),
        *a3,
        28);
    }
    v7 = -1073676268;
    *v5 = 28;
  }
  return v7;
}

```

## disassembly

```asm
0x14001e7b8  mov     r11, rsp
0x14001e7bb  push    rbx
0x14001e7bc  push    rsi
0x14001e7bd  push    rdi
0x14001e7be  push    r14
0x14001e7c0  push    r15
0x14001e7c2  sub     rsp, 70h
0x14001e7c6  mov     rdi, rdx
0x14001e7c9  mov     qword ptr [r11-48h], 0
0x14001e7d1  mov     edx, [r8]
0x14001e7d4  mov     r15d, 1Ch
0x14001e7da  mov     qword ptr [r11-40h], 0
0x14001e7e2  mov     r14, r8
0x14001e7e5  mov     rsi, rcx
0x14001e7e8  cmp     edx, r15d
0x14001e7eb  jnb     short loc_14001E83E
0x14001e7ed  lea     rax, WPP_RECORDER_INITIALIZED
0x14001e7f4  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x14001e7fb  jz      short loc_14001E831
0x14001e7fd  mov     eax, [rcx+10h]
0x14001e800  lea     r9d, [r15+8]
0x14001e804  mov     rcx, cs:WPP_GLOBAL_Control
0x14001e80b  lea     r8d, [r15-19h]
0x14001e80f  mov     [r11-60h], r15d
0x14001e813  mov     dword ptr [rsp+98h+var_68], edx
0x14001e817  mov     dl, 2
0x14001e819  mov     [rsp+98h+var_70], eax
0x14001e81d  lea     rax, WPP_dce8bfe23d3239629ed9d053a5b71e5e_Traceguids
0x14001e824  mov     rcx, [rcx+40h]
0x14001e828  mov     [r11-78h], rax
0x14001e82c  call    WPP_RECORDER_SF_Ddd
0x14001e831  mov     ebx, 0C0010014h
0x14001e836  mov     [r14], r15d
0x14001e839  jmp     loc_14001EA00
0x14001e83e  movzx   r9d, byte ptr [rdi]
0x14001e842  cmp     r9b, 80h
0x14001e846  jnz     loc_14001E9A9
0x14001e84c  cmp     [rdi+2], r15w
0x14001e851  jb      loc_14001E9A9
0x14001e857  mov     r8d, 1
0x14001e85d  cmp     [rdi+1], r8b
0x14001e861  jb      loc_14001E9A9
0x14001e867  mov     r10d, [rdi+18h]
0x14001e86b  lea     rcx, [r15+r10]
0x14001e86f  cmp     rcx, rdx
0x14001e872  jbe     short loc_14001E8CD
0x14001e874  lea     rax, WPP_RECORDER_INITIALIZED
0x14001e87b  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x14001e882  jz      short loc_14001E8BA
0x14001e884  mov     eax, [rsi+10h]
0x14001e887  lea     r9d, [r8+25h]
0x14001e88b  mov     rcx, cs:WPP_GLOBAL_Control
0x14001e892  lea     r8d, [r9-23h]
0x14001e896  mov     [rsp+98h+var_60], r15d
0x14001e89b  mov     dword ptr [rsp+98h+var_68], edx
0x14001e89f  mov     dl, 2
0x14001e8a1  mov     [rsp+98h+var_70], eax
0x14001e8a5  lea     rax, WPP_dce8bfe23d3239629ed9d053a5b71e5e_Traceguids
0x14001e8ac  mov     rcx, [rcx+40h]
0x14001e8b0  mov     [rsp+98h+var_78], rax
0x14001e8b5  call    WPP_RECORDER_SF_Ddd
0x14001e8ba  mov     eax, [rdi+18h]
0x14001e8bd  mov     ebx, 0C0010014h
0x14001e8c2  add     eax, r15d
0x14001e8c5  mov     [r14], eax
0x14001e8c8  jmp     loc_14001EA00
0x14001e8cd  cmp     qword ptr [rsi+1A8h], 0
0x14001e8d5  movups  xmm0, xmmword ptr [rdi+4]
0x14001e8d9  mov     eax, [rdi+14h]
0x14001e8dc  mov     [rsp+98h+var_38], eax
0x14001e8e0  movdqu  [rsp+98h+var_48], xmm0
0x14001e8e6  jnz     short loc_14001E8F1
0x14001e8e8  cmp     byte ptr [rsi+240h], 0
0x14001e8ef  jz      short loc_14001E8FA
0x14001e8f1  cmp     byte ptr [rsi+1C4h], 0
0x14001e8f8  jnz     short loc_14001E8FD
0x14001e8fa  xor     r8d, r8d
0x14001e8fd  lea     r9, [rdi+1Ch]
0x14001e901  mov     dword ptr [rsp+98h+var_78], r10d
0x14001e906  lea     rdx, [rsp+98h+var_48]
0x14001e90b  mov     rcx, rsi
0x14001e90e  call    ?MbbUtilSetupCommandMessage@@YAHPEAU_MBB_REQUEST_CONTEXT@@PEAU_MBB_COMMAND@@W4_MBB_COMMAND_TYPE@@PEAEK@Z; MbbUtilSetupCommandMessage(_MBB_REQUEST_CONTEXT *,_MBB_COMMAND *,_MBB_COMMAND_TYPE,uchar *,ulong)
0x14001e913  mov     ebx, eax
0x14001e915  test    eax, eax
0x14001e917  jz      short loc_14001E967
0x14001e919  lea     rax, WPP_RECORDER_INITIALIZED
0x14001e920  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x14001e927  jz      loc_14001EA00
0x14001e92d  mov     ecx, [rsi+10h]
0x14001e930  mov     r9d, 27h ; '''
0x14001e936  mov     dword ptr [rsp+98h+var_68], ebx
0x14001e93a  mov     [rsp+98h+var_70], ecx
0x14001e93e  mov     rcx, cs:WPP_GLOBAL_Control
0x14001e945  lea     rax, WPP_dce8bfe23d3239629ed9d053a5b71e5e_Traceguids
0x14001e94c  mov     r8d, 3
0x14001e952  mov     [rsp+98h+var_78], rax
0x14001e957  mov     dl, 2
0x14001e959  mov     rcx, [rcx+40h]
0x14001e95d  call    WPP_RECORDER_SF_DD
0x14001e962  jmp     loc_14001EA00
0x14001e967  mov     eax, [rdi+18h]
0x14001e96a  mov     rcx, rsi; struct _MBB_REQUEST_CONTEXT *
0x14001e96d  add     [r14], eax
0x14001e970  call    ?MbbUtilSendMessageFragmentsAndLog@@YAHPEAU_MBB_REQUEST_CONTEXT@@@Z; MbbUtilSendMessageFragmentsAndLog(_MBB_REQUEST_CONTEXT *)
0x14001e975  mov     ebx, eax
0x14001e977  test    eax, eax
0x14001e979  jz      loc_14001EA00
0x14001e97f  cmp     eax, 103h
0x14001e984  jz      short loc_14001EA00
0x14001e986  lea     rax, WPP_RECORDER_INITIALIZED
0x14001e98d  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x14001e994  jz      short loc_14001EA00
0x14001e996  mov     eax, [rsi+10h]
0x14001e999  mov     r9d, 28h ; '('
0x14001e99f  mov     dword ptr [rsp+98h+var_68], ebx
0x14001e9a3  mov     [rsp+98h+var_70], eax
0x14001e9a7  jmp     short loc_14001E93E
0x14001e9a9  lea     rax, WPP_RECORDER_INITIALIZED
0x14001e9b0  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x14001e9b7  jz      short loc_14001E9FB
0x14001e9b9  movzx   eax, byte ptr [rdi+1]
0x14001e9bd  mov     edx, r9d
0x14001e9c0  movzx   ecx, word ptr [rdi+2]
0x14001e9c4  mov     r9d, 25h ; '%'
0x14001e9ca  mov     [rsp+98h+var_58], eax
0x14001e9ce  mov     eax, [rsi+10h]
0x14001e9d1  mov     [rsp+98h+var_60], ecx
0x14001e9d5  mov     rcx, cs:WPP_GLOBAL_Control
0x14001e9dc  mov     dword ptr [rsp+98h+var_68], edx
0x14001e9e0  mov     dl, 2
0x14001e9e2  mov     [rsp+98h+var_70], eax
0x14001e9e6  lea     rax, WPP_dce8bfe23d3239629ed9d053a5b71e5e_Traceguids
0x14001e9ed  mov     [rsp+98h+var_78], rax
0x14001e9f2  mov     rcx, [rcx+40h]
0x14001e9f6  call    WPP_RECORDER_SF_DDdd
0x14001e9fb  mov     ebx, 0C0010015h
0x14001ea00  mov     eax, ebx
0x14001ea02  add     rsp, 70h
0x14001ea06  pop     r15
0x14001ea08  pop     r14
0x14001ea0a  pop     rdi
0x14001ea0b  pop     rsi
0x14001ea0c  pop     rbx
0x14001ea0d  retn
```
