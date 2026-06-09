# AipLaunchProcessWithIdentityHelper(_RPC_ASYNC_STATE *,void *,ushort const *,ushort *,ulong,ulong,ushort const *,ushort const *,_APPINFO_STARTUPINFO *,_STARTUPINFO_STDHANDLES *,ushort const *,ushort const *,unsigned __int64,ulong,ulong,AicAgenticFlags,void *,unsigned __int64,unsigned __int64 *,_GUID *,unsigned __int64,char const *,int *,UACPROMPT_POLICY *,_APPINFO_PROCESS_INFORMATION *)

- ea: `0x18002ebec`
- end: `0x18002ed91`
- name: `?AipLaunchProcessWithIdentityHelper@@YAXPEAU_RPC_ASYNC_STATE@@PEAXPEBGPEAGKK22PEAU_APPINFO_STARTUPINFO@@PEAU_STARTUPINFO_STDHANDLES@@22_KKKW4AicAgenticFlags@@16PEA_KPEAU_GUID@@6PEBDPEAHPEAW4UACPROMPT_POLICY@@PEAU_APPINFO_PROCESS_INFORMATION@@@Z`
- size: `421`
- prototype: `_UNKNOWN **__fastcall(struct _RPC_ASYNC_STATE *, void *, unsigned __int16 *, unsigned __int16 *, unsigned int, unsigned int, unsigned __int16 *, unsigned __int16 *, struct _APPINFO_STARTUPINFO *, __int64, unsigned __int16 *, unsigned __int16 *, unsigned __int64, unsigned int, unsigned int, unsigned int Reply, void *, unsigned __int64, unsigned __int64 *, struct _GUID *, unsigned __int64, char *, int *, enum UACPROMPT_POLICY *, struct _APPINFO_PROCESS_INFORMATION *)`
- caller_count: `2`
- callee_count: `3`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x18003d070`
- `0x18003e130`

## callees

- `0x180026f40`
- `0x18002ebec`
- `0x18002ed98`

## import_xrefs

- `RPCRT4!RpcAsyncCompleteCall` at `0x18002ed44`
- `RPCRT4!RpcAsyncCompleteCall` at `0x18002ed44`

## pseudocode

```c
_UNKNOWN **__fastcall AipLaunchProcessWithIdentityHelper(
        struct _RPC_ASYNC_STATE *a1,
        void *a2,
        unsigned __int16 *a3,
        unsigned __int16 *a4,
        unsigned int a5,
        unsigned int a6,
        unsigned __int16 *a7,
        unsigned __int16 *a8,
        struct _APPINFO_STARTUPINFO *a9,
        __int64 a10,
        unsigned __int16 *a11,
        unsigned __int16 *a12,
        unsigned __int64 a13,
        unsigned int a14,
        unsigned int a15,
        unsigned int Reply,
        void *a17,
        unsigned __int64 a18,
        unsigned __int64 *a19,
        struct _GUID *a20,
        unsigned __int64 a21,
        char *a22,
        int *a23,
        enum UACPROMPT_POLICY *a24,
        struct _APPINFO_PROCESS_INFORMATION *a25)
{
  _UNKNOWN **result; // rax

  Reply = AipLaunchProcessWithIdentityImplementation(
            a2,
            a3,
            a4,
            a5,
            a6,
            a7,
            a8,
            a9,
            0,
            0,
            0,
            a11,
            a12,
            a13,
            a14,
            a15,
            0,
            a17,
            a18,
            a19,
            a20,
            a21,
            a22,
            a23,
            a24,
            (void **)a25);
  RpcAsyncCompleteCall(a1, &Reply);
  result = &WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    return (_UNKNOWN **)WPP_SF_D(
                          *((_QWORD *)WPP_GLOBAL_Control + 2),
                          43,
                          WPP_b23fa736e9853481a42645a0499c03f5_Traceguids,
                          Reply);
  return result;
}

```

## disassembly

```asm
0x18002ebec  mov     [rsp+arg_0], rbx
0x18002ebf1  push    rdi
0x18002ebf2  sub     rsp, 0D0h
0x18002ebf9  mov     rax, [rsp+0D8h+arg_C0]
0x18002ec01  mov     rdi, rcx
0x18002ec04  mov     [rsp+0D8h+var_10], rax; struct _APPINFO_PROCESS_INFORMATION *
0x18002ec0c  xor     ecx, ecx
0x18002ec0e  mov     rax, [rsp+0D8h+arg_B8]
0x18002ec16  mov     r10, r9
0x18002ec19  mov     [rsp+0D8h+var_18], rax; enum UACPROMPT_POLICY *
0x18002ec21  mov     r11, r8
0x18002ec24  mov     rax, [rsp+0D8h+arg_B0]
0x18002ec2c  mov     rbx, rdx
0x18002ec2f  mov     [rsp+0D8h+var_20], rax; int *
0x18002ec37  mov     r8, r10; unsigned __int16 *
0x18002ec3a  mov     rax, [rsp+0D8h+arg_A8]
0x18002ec42  mov     rdx, r11; unsigned __int16 *
0x18002ec45  mov     [rsp+0D8h+var_28], rax; char *
0x18002ec4d  mov     rax, [rsp+0D8h+arg_A0]
0x18002ec55  mov     r9d, [rsp+0D8h+arg_20]; unsigned int
0x18002ec5d  mov     [rsp+0D8h+var_30], rax; unsigned __int64
0x18002ec65  mov     rax, [rsp+0D8h+arg_98]
0x18002ec6d  mov     [rsp+0D8h+var_38], rax; struct _GUID *
0x18002ec75  mov     rax, [rsp+0D8h+arg_90]
0x18002ec7d  mov     [rsp+0D8h+var_40], rax; unsigned __int64 *
0x18002ec85  mov     rax, [rsp+0D8h+arg_88]
0x18002ec8d  mov     [rsp+0D8h+var_48], rax; unsigned __int64
0x18002ec95  mov     rax, [rsp+0D8h+arg_80]
0x18002ec9d  mov     [rsp+0D8h+var_50], rax; void *
0x18002eca5  mov     eax, [rsp+0D8h+arg_70]
0x18002ecac  mov     [rsp+0D8h+var_58], ecx; unsigned int
0x18002ecb3  mov     [rsp+0D8h+var_60], eax; unsigned int
0x18002ecb7  mov     eax, [rsp+0D8h+arg_68]
0x18002ecbe  mov     [rsp+0D8h+var_68], eax; unsigned int
0x18002ecc2  mov     rax, [rsp+0D8h+arg_60]
0x18002ecca  mov     [rsp+0D8h+var_70], rax; unsigned __int64
0x18002eccf  mov     rax, [rsp+0D8h+arg_58]
0x18002ecd7  mov     [rsp+0D8h+var_78], rax; unsigned __int16 *
0x18002ecdc  mov     rax, [rsp+0D8h+arg_50]
0x18002ece4  mov     [rsp+0D8h+var_80], rax; unsigned __int16 *
0x18002ece9  mov     rax, [rsp+0D8h+arg_40]
0x18002ecf1  mov     [rsp+0D8h+var_88], rcx; unsigned __int64
0x18002ecf6  mov     [rsp+0D8h+var_90], rcx; unsigned __int16 **
0x18002ecfb  mov     [rsp+0D8h+var_98], rcx; struct _STARTUPINFO_STDHANDLES *
0x18002ed00  mov     rcx, rbx; void *
0x18002ed03  mov     [rsp+0D8h+var_A0], rax; struct _APPINFO_STARTUPINFO *
0x18002ed08  mov     rax, [rsp+0D8h+arg_38]
0x18002ed10  mov     [rsp+0D8h+var_A8], rax; unsigned __int16 *
0x18002ed15  mov     rax, [rsp+0D8h+arg_30]
0x18002ed1d  mov     [rsp+0D8h+var_B0], rax; unsigned __int16 *
0x18002ed22  mov     eax, [rsp+0D8h+arg_28]
0x18002ed29  mov     [rsp+0D8h+var_B8], eax; unsigned int
0x18002ed2d  call    ?AipLaunchProcessWithIdentityImplementation@@YAKPEAXPEBGPEAGKK11PEAU_APPINFO_STARTUPINFO@@PEAU_STARTUPINFO_STDHANDLES@@PEAPEAG_K116KKK06PEA_KPEAU_GUID@@6PEBDPEAHPEAW4UACPROMPT_POLICY@@PEAU_APPINFO_PROCESS_INFORMATION@@@Z; AipLaunchProcessWithIdentityImplementation(void *,ushort const *,ushort *,ulong,ulong,ushort const *,ushort const *,_APPINFO_STARTUPINFO *,_STARTUPINFO_STDHANDLES *,ushort * *,unsigned __int64,ushort const *,ushort const *,unsigned __int64,ulong,ulong,ulong,void *,unsigned __int64,unsigned __int64 *,_GUID *,unsigned __int64,char const *,int *,UACPROMPT_POLICY *,_APPINFO_PROCESS_INFORMATION *)
0x18002ed32  lea     rdx, [rsp+0D8h+Reply]; Reply
0x18002ed3a  mov     [rsp+0D8h+Reply], eax
0x18002ed41  mov     rcx, rdi; pAsync
0x18002ed44  call    cs:__imp_RpcAsyncCompleteCall
0x18002ed4a  mov     rcx, cs:WPP_GLOBAL_Control
0x18002ed51  lea     rax, WPP_GLOBAL_Control
0x18002ed58  cmp     rcx, rax
0x18002ed5b  jz      short loc_18002ED80
0x18002ed5d  test    byte ptr [rcx+1Ch], 1
0x18002ed61  jz      short loc_18002ED80
0x18002ed63  mov     r9d, [rsp+0D8h+Reply]
0x18002ed6b  lea     r8, WPP_b23fa736e9853481a42645a0499c03f5_Traceguids
0x18002ed72  mov     rcx, [rcx+10h]
0x18002ed76  mov     edx, 2Bh ; '+'
0x18002ed7b  call    WPP_SF_D
0x18002ed80  mov     rbx, [rsp+0D8h+arg_0]
0x18002ed88  add     rsp, 0D0h
0x18002ed8f  pop     rdi
0x18002ed90  retn
```
