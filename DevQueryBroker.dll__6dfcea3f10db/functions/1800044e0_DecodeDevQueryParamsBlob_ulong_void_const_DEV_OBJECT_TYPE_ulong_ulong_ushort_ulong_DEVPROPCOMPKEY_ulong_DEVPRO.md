# DecodeDevQueryParamsBlob(ulong,void const *,_DEV_OBJECT_TYPE *,ulong *,ulong *,ushort * * *,ulong *,_DEVPROPCOMPKEY * *,ulong *,_DEVPROP_FILTER_EXPRESSION * *,ulong *,_DEV_QUERY_PARAMETER * *,ushort * *)

- ea: `0x1800044e0`
- end: `0x1800046db`
- name: `?DecodeDevQueryParamsBlob@@YAJKPEBXPEAW4_DEV_OBJECT_TYPE@@PEAK2PEAPEAPEAG2PEAPEAU_DEVPROPCOMPKEY@@2PEAPEAU_DEVPROP_FILTER_EXPRESSION@@2PEAPEAU_DEV_QUERY_PARAMETER@@PEAPEAG@Z`
- size: `507`
- prototype: `__int64 __fastcall(unsigned int BufferSize, char *Buffer, enum _DEV_OBJECT_TYPE *, unsigned int *, unsigned int *, unsigned __int16 ***, unsigned int *, struct _DEVPROPCOMPKEY **, unsigned int *, struct _DEVPROP_FILTER_EXPRESSION **, unsigned int *, struct _DEV_QUERY_PARAMETER **, unsigned __int16 **)`
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x180003f80`

## callees

- `0x1800044e0`

## import_xrefs

- `msvcrt!_aligned_free` at `0x180004692`
- `msvcrt!_aligned_free` at `0x180004692`
- `RPCRT4!MesDecodeBufferHandleCreate` at `0x1800045cf`
- `RPCRT4!MesDecodeBufferHandleCreate` at `0x1800045cf`
- `RPCRT4!NdrMesTypeDecode3` at `0x180004619`
- `RPCRT4!NdrMesTypeDecode3` at `0x180004619`
- `RPCRT4!MesHandleFree` at `0x1800046bb`
- `RPCRT4!MesHandleFree` at `0x1800046bb`
- `RPCRT4!RpcExceptionFilter` at `0x18000a5c5`
- `RPCRT4!RpcExceptionFilter` at `0x18000a5c5`

## pseudocode

```c
__int64 __fastcall DecodeDevQueryParamsBlob(
        unsigned int BufferSize,
        char *Buffer,
        enum _DEV_OBJECT_TYPE *a3,
        unsigned int *a4,
        unsigned int *a5,
        unsigned __int16 ***a6,
        unsigned int *a7,
        struct _DEVPROPCOMPKEY **a8,
        unsigned int *a9,
        struct _DEVPROP_FILTER_EXPRESSION **a10,
        unsigned int *a11,
        struct _DEV_QUERY_PARAMETER **a12,
        unsigned __int16 **a13)
{
  RPC_STATUS v14; // eax
  signed int v15; // ebx
  _DWORD *v16; // rcx
  handle_t Handle; // [rsp+30h] [rbp-38h] BYREF
  void *Block; // [rsp+38h] [rbp-30h] BYREF

  Handle = 0;
  Block = 0;
  if ( BufferSize && Buffer && a3 && a4 && a5 && a6 && a7 && a8 && a9 && a10 && a11 && a12 && a13 )
  {
    v14 = MesDecodeBufferHandleCreate(Buffer, BufferSize, &Handle);
    v15 = v14;
    if ( v14 >= 1 )
      v15 = (unsigned __int16)v14 | 0x80010000;
    if ( v15 >= 0 )
    {
      NdrMesTypeDecode3(Handle, &stru_18000E958, &stru_18000D440, (const unsigned int **)&off_180011018, 0, &Block);
      v16 = Block;
      *(_DWORD *)a3 = *(_DWORD *)Block;
      *a4 = v16[1];
      *a5 = v16[2];
      *a6 = (unsigned __int16 **)*((_QWORD *)v16 + 2);
      *a7 = v16[6];
      *a8 = (struct _DEVPROPCOMPKEY *)*((_QWORD *)v16 + 4);
      *a9 = v16[10];
      *a10 = (struct _DEVPROP_FILTER_EXPRESSION *)*((_QWORD *)v16 + 6);
      *a11 = v16[14];
      *a12 = (struct _DEV_QUERY_PARAMETER *)*((_QWORD *)v16 + 8);
      *a13 = (unsigned __int16 *)*((_QWORD *)v16 + 9);
      _aligned_free(v16);
    }
  }
  else
  {
    v15 = -2147024809;
  }
  if ( Handle )
    MesHandleFree(Handle);
  return (unsigned int)v15;
}

```

## disassembly

```asm
0x1800044e0  mov     r11, rsp
0x1800044e3  mov     [r11+8], rbx
0x1800044e7  mov     [r11+10h], rsi
0x1800044eb  mov     [r11+18h], r8
0x1800044ef  push    rdi
0x1800044f0  push    r12
0x1800044f2  push    r13
0x1800044f4  push    r14
0x1800044f6  push    r15
0x1800044f8  sub     rsp, 40h
0x1800044fc  mov     r13, r9
0x1800044ff  mov     rax, rdx
0x180004502  mov     qword ptr [r11-38h], 0
0x18000450a  mov     qword ptr [r11-30h], 0
0x180004512  test    ecx, ecx
0x180004514  jz      loc_1800046AC
0x18000451a  test    rax, rax
0x18000451d  jz      loc_1800046AC
0x180004523  test    r8, r8
0x180004526  jz      loc_1800046AC
0x18000452c  test    r9, r9
0x18000452f  jz      loc_1800046AC
0x180004535  mov     rdi, [rsp+68h+arg_20]
0x18000453d  test    rdi, rdi
0x180004540  jz      loc_1800046AC
0x180004546  mov     rsi, [rsp+68h+arg_28]
0x18000454e  test    rsi, rsi
0x180004551  jz      loc_1800046AC
0x180004557  mov     r14, [rsp+68h+arg_30]
0x18000455f  test    r14, r14
0x180004562  jz      loc_1800046AC
0x180004568  mov     r15, [rsp+68h+arg_38]
0x180004570  test    r15, r15
0x180004573  jz      loc_1800046AC
0x180004579  mov     r12, [rsp+68h+arg_40]
0x180004581  test    r12, r12
0x180004584  jz      loc_1800046AC
0x18000458a  cmp     [rsp+68h+arg_48], 0
0x180004593  jz      loc_1800046AC
0x180004599  cmp     [rsp+68h+arg_50], 0
0x1800045a2  jz      loc_1800046AC
0x1800045a8  cmp     [rsp+68h+arg_58], 0
0x1800045b1  jz      loc_1800046AC
0x1800045b7  cmp     [rsp+68h+arg_60], 0
0x1800045c0  jz      loc_1800046AC
0x1800045c6  lea     r8, [r11-38h]; pHandle
0x1800045ca  mov     edx, ecx; BufferSize
0x1800045cc  mov     rcx, rax; Buffer
0x1800045cf  call    cs:__imp_MesDecodeBufferHandleCreate
0x1800045d5  mov     ebx, eax
0x1800045d7  cmp     eax, 1
0x1800045da  jl      short loc_1800045E5
0x1800045dc  movzx   ebx, ax
0x1800045df  or      ebx, 80010000h
0x1800045e5  test    ebx, ebx
0x1800045e7  js      loc_1800046B1
0x1800045ed  lea     rax, [rsp+68h+Block]
0x1800045f2  mov     [rsp+68h+pObject], rax; pObject
0x1800045f7  mov     [rsp+68h+nTypeIndex], 0; nTypeIndex
0x1800045ff  lea     r9, off_180011018; ArrTypeOffset
0x180004606  lea     r8, stru_18000D440; pProxyInfo
0x18000460d  lea     rdx, stru_18000E958; pPicklingInfo
0x180004614  mov     rcx, [rsp+68h+Handle]; Handle
0x180004619  call    cs:__imp_NdrMesTypeDecode3
0x18000461f  nop
0x180004620  mov     rcx, [rsp+68h+Block]; Block
0x180004625  mov     eax, [rcx]
0x180004627  mov     rdx, [rsp+68h+arg_10]
0x18000462f  mov     [rdx], eax
0x180004631  mov     eax, [rcx+4]
0x180004634  mov     [r13+0], eax
0x180004638  mov     eax, [rcx+8]
0x18000463b  mov     [rdi], eax
0x18000463d  mov     rax, [rcx+10h]
0x180004641  mov     [rsi], rax
0x180004644  mov     eax, [rcx+18h]
0x180004647  mov     [r14], eax
0x18000464a  mov     rax, [rcx+20h]
0x18000464e  mov     [r15], rax
0x180004651  mov     eax, [rcx+28h]
0x180004654  mov     [r12], eax
0x180004658  mov     rax, [rcx+30h]
0x18000465c  mov     rdx, [rsp+68h+arg_48]
0x180004664  mov     [rdx], rax
0x180004667  mov     eax, [rcx+38h]
0x18000466a  mov     rdx, [rsp+68h+arg_50]
0x180004672  mov     [rdx], eax
0x180004674  mov     rax, [rcx+40h]
0x180004678  mov     rdx, [rsp+68h+arg_58]
0x180004680  mov     [rdx], rax
0x180004683  mov     rax, [rcx+48h]
0x180004687  mov     rdx, [rsp+68h+arg_60]
0x18000468f  mov     [rdx], rax
0x180004692  call    cs:__imp__aligned_free
0x180004698  jmp     short loc_1800046B1
0x18000469a  mov     ebx, eax
0x18000469c  cmp     eax, 1
0x18000469f  jl      short loc_1800046AA
0x1800046a1  movzx   ebx, ax
0x1800046a4  or      ebx, 80010000h
0x1800046aa  jmp     short loc_1800046B1
0x1800046ac  mov     ebx, 80070057h
0x1800046b1  mov     rcx, [rsp+68h+Handle]; Handle
0x1800046b6  test    rcx, rcx
0x1800046b9  jz      short loc_1800046C1
0x1800046bb  call    cs:__imp_MesHandleFree
0x1800046c1  mov     eax, ebx
0x1800046c3  mov     rbx, [rsp+68h+arg_0]
0x1800046c8  mov     rsi, [rsp+68h+arg_8]
0x1800046cd  add     rsp, 40h
0x1800046d1  pop     r15
0x1800046d3  pop     r14
0x1800046d5  pop     r13
0x1800046d7  pop     r12
0x1800046d9  pop     rdi
0x1800046da  retn
0x18000a5b7  push    rbp
0x18000a5b9  sub     rsp, 30h
0x18000a5bd  mov     rbp, rdx
0x18000a5c0  mov     rcx, [rcx]
0x18000a5c3  mov     ecx, [rcx]; ExceptionCode
0x18000a5c5  call    cs:__imp_RpcExceptionFilter
0x18000a5cb  nop
0x18000a5cc  add     rsp, 30h
0x18000a5d0  pop     rbp
0x18000a5d1  retn
```
