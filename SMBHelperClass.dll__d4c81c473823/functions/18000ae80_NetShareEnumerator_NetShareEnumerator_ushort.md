# NetShareEnumerator::NetShareEnumerator(ushort *)

- ea: `0x18000ae80`
- end: `0x18000af6e`
- name: `??0NetShareEnumerator@@QEAA@PEAG@Z`
- size: `238`
- prototype: `NetShareEnumerator *__fastcall(NetShareEnumerator *this, unsigned __int16 *)`
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18000a690`

## callees

- `0x18000257c`
- `0x18000ae80`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18000aef5`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18000aef5`
- `srvcli!NetShareEnum` at `0x18000af29`
- `srvcli!NetShareEnum` at `0x18000af29`

## pseudocode

```c
NetShareEnumerator *__fastcall NetShareEnumerator::NetShareEnumerator(NetShareEnumerator *this, unsigned __int16 *a2)
{
  DWORD *resume_handle; // r14
  DWORD *v3; // rbp
  _QWORD *v4; // rdi
  DWORD v7; // eax
  DWORD totalentries; // [rsp+70h] [rbp+8h] BYREF
  ulong pExceptionObject; // [rsp+78h] [rbp+10h] BYREF

  *((_QWORD *)this + 4) = a2;
  resume_handle = (DWORD *)((char *)this + 8);
  v3 = (DWORD *)((char *)this + 24);
  *((_QWORD *)this + 2) = 0;
  v4 = (_QWORD *)((char *)this + 40);
  *((_DWORD *)this + 7) = 0;
  *((_DWORD *)this + 12) = 0;
  *((_DWORD *)this + 2) = 0;
  *((_DWORD *)this + 6) = 0;
  *(_QWORD *)this = &NetShareEnumerator::`vftable';
  totalentries = 0;
  if ( CoCreateInstance(&CLSID_NDFEtw, 0, 1u, &IID_INDFEtw, (LPVOID *)this + 5) )
    *v4 = 0;
  v7 = NetShareEnum(a2, 0, (LPBYTE *)this + 2, 0x400u, v3, &totalentries, resume_handle);
  if ( v7 )
  {
    if ( v7 != 234 )
    {
      pExceptionObject = v7;
      throw &pExceptionObject;
    }
    *((_DWORD *)this + 12) = 1;
  }
  return this;
}

```

## disassembly

```asm
0x18000ae80  mov     [rsp+arg_10], rbx
0x18000ae85  push    rbp
0x18000ae86  push    rsi
0x18000ae87  push    rdi
0x18000ae88  push    r14
0x18000ae8a  push    r15
0x18000ae8c  sub     rsp, 40h
0x18000ae90  mov     [rcx+20h], rdx
0x18000ae94  lea     r14, [rcx+8]
0x18000ae98  lea     rbp, [rcx+18h]
0x18000ae9c  mov     qword ptr [rcx+10h], 0
0x18000aea4  lea     rdi, [rcx+28h]
0x18000aea8  mov     dword ptr [rcx+1Ch], 0
0x18000aeaf  mov     rsi, rdx
0x18000aeb2  mov     dword ptr [rcx+30h], 0
0x18000aeb9  xor     edx, edx; pUnkOuter
0x18000aebb  mov     dword ptr [r14], 0
0x18000aec2  lea     rax, ??_7NetShareEnumerator@@6B@; const NetShareEnumerator::`vftable'
0x18000aec9  mov     dword ptr [rbp+0], 0
0x18000aed0  mov     rbx, rcx
0x18000aed3  mov     [rcx], rax
0x18000aed6  lea     r9, IID_INDFEtw; riid
0x18000aedd  mov     [rsp+68h+arg_0], 0
0x18000aee5  lea     r8d, [rdx+1]; dwClsContext
0x18000aee9  mov     [rsp+68h+ppv], rdi; ppv
0x18000aeee  lea     rcx, CLSID_NDFEtw; rclsid
0x18000aef5  call    cs:__imp_CoCreateInstance
0x18000aefb  test    eax, eax
0x18000aefd  jz      short loc_18000AF06
0x18000aeff  mov     qword ptr [rdi], 0
0x18000af06  lea     rax, [rsp+68h+arg_0]
0x18000af0b  mov     [rsp+68h+resume_handle], r14; resume_handle
0x18000af10  mov     [rsp+68h+totalentries], rax; totalentries
0x18000af15  lea     r8, [rbx+10h]; bufptr
0x18000af19  mov     r9d, 400h; prefmaxlen
0x18000af1f  mov     [rsp+68h+ppv], rbp; entriesread
0x18000af24  xor     edx, edx; level
0x18000af26  mov     rcx, rsi; servername
0x18000af29  call    cs:__imp_NetShareEnum
0x18000af2f  test    eax, eax
0x18000af31  jz      short loc_18000AF41
0x18000af33  cmp     eax, 0EAh
0x18000af38  jnz     short loc_18000AF58
0x18000af3a  mov     dword ptr [rbx+30h], 1
0x18000af41  mov     rax, rbx
0x18000af44  mov     rbx, [rsp+68h+arg_10]
0x18000af4c  add     rsp, 40h
0x18000af50  pop     r15
0x18000af52  pop     r14
0x18000af54  pop     rdi
0x18000af55  pop     rsi
0x18000af56  pop     rbp
0x18000af57  retn
0x18000af58  lea     rdx, _TI1K; pThrowInfo
0x18000af5f  mov     [rsp+68h+pExceptionObject], eax
0x18000af63  lea     rcx, [rsp+68h+pExceptionObject]; pExceptionObject
0x18000af68  call    _CxxThrowException_0
```
