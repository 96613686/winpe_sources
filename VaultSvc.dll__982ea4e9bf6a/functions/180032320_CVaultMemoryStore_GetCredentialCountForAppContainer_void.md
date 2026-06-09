# CVaultMemoryStore::GetCredentialCountForAppContainer(void *)

- ea: `0x180032320`
- end: `0x18003243c`
- name: `?GetCredentialCountForAppContainer@CVaultMemoryStore@@UEAAKPEAX@Z`
- size: `284`
- prototype: `__int64 __fastcall(struct _RTL_RESOURCE *this, void *)`
- caller_count: `0`
- callee_count: `5`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callees

- `0x180032320`
- `0x18003a580`
- `0x18003af10`
- `0x18004b430`
- `0x18004b43c`

## import_xrefs

- `ntdll!RtlReleaseResource` at `0x180032414`
- `ntdll!RtlReleaseResource` at `0x180032414`
- `ntdll!RtlAcquireResourceShared` at `0x180032364`
- `ntdll!RtlAcquireResourceShared` at `0x180032364`
- `ntdll!RtlLengthSid` at `0x180032382`
- `ntdll!RtlLengthSid` at `0x180032382`

## pseudocode

```c
__int64 __fastcall CVaultMemoryStore::GetCredentialCountForAppContainer(struct _RTL_RESOURCE *this, void *a2)
{
  struct _RTL_RESOURCE *v5; // r14
  char v6; // si
  ULONG v7; // eax
  char *SharedSemaphore; // rbp
  char *v9; // rbx
  _BYTE *v10; // rdi
  char v11; // cl
  _BYTE **v12; // rax
  unsigned int v13; // ebx
  _BYTE Buf2[80]; // [rsp+40h] [rbp-98h] BYREF

  if ( !a2 )
    return 0;
  v5 = this + 2;
  v6 = 1;
  RtlAcquireResourceShared(this + 2, 1u);
  memset_0(Buf2, 0, 0x44u);
  v7 = RtlLengthSid(a2);
  memcpy_0(Buf2, a2, v7);
  SharedSemaphore = (char *)this->SharedSemaphore;
  v9 = SharedSemaphore;
  v10 = (_BYTE *)*((_QWORD *)SharedSemaphore + 1);
  if ( !v10[25] )
  {
    do
    {
      if ( memcmp_0(v10 + 28, Buf2, 0x44u) >= 0 )
      {
        v11 = 0;
        v9 = v10;
      }
      else
      {
        v11 = 1;
      }
      v12 = (_BYTE **)(v10 + 16);
      if ( !v11 )
        v12 = (_BYTE **)v10;
      v10 = *v12;
    }
    while ( !(*v12)[25] );
  }
  if ( v9[25] || memcmp_0(Buf2, v9 + 28, 0x44u) < 0 )
    v6 = 0;
  if ( !v6 )
    v9 = SharedSemaphore;
  if ( v9 == SharedSemaphore )
    v13 = 0;
  else
    v13 = *((_DWORD *)v9 + 24);
  RtlReleaseResource(v5);
  return v13;
}

```

## disassembly

```asm
0x180032320  push    rbx
0x180032322  push    rbp
0x180032323  push    rsi
0x180032324  push    rdi
0x180032325  push    r12
0x180032327  push    r14
0x180032329  sub     rsp, 0A8h
0x180032330  mov     rax, cs:__security_cookie
0x180032337  xor     rax, rsp
0x18003233a  mov     [rsp+0D8h+var_48], rax
0x180032342  mov     rbx, rdx
0x180032345  mov     rbp, rcx
0x180032348  test    rdx, rdx
0x18003234b  jnz     short loc_180032354
0x18003234d  xor     eax, eax
0x18003234f  jmp     loc_18003241C
0x180032354  lea     r14, [rcx+0C0h]
0x18003235b  mov     sil, 1
0x18003235e  mov     dl, sil; Wait
0x180032361  mov     rcx, r14; Resource
0x180032364  call    cs:__imp_RtlAcquireResourceShared
0x18003236a  mov     r12d, 44h ; 'D'
0x180032370  lea     rcx, [rsp+0D8h+Buf2]; void *
0x180032375  mov     r8d, r12d; Size
0x180032378  xor     edx, edx; Val
0x18003237a  call    memset_0
0x18003237f  mov     rcx, rbx; Sid
0x180032382  call    cs:__imp_RtlLengthSid
0x180032388  mov     r8d, eax; Size
0x18003238b  mov     rdx, rbx; Src
0x18003238e  lea     rcx, [rsp+0D8h+Buf2]; void *
0x180032393  call    memcpy_0
0x180032398  mov     rbp, [rbp+28h]
0x18003239c  xor     eax, eax
0x18003239e  mov     [rsp+0D8h+var_AC], eax
0x1800323a2  mov     rbx, rbp
0x1800323a5  mov     rdi, [rbp+8]
0x1800323a9  cmp     [rdi+19h], al
0x1800323ac  jnz     short loc_1800323E0
0x1800323ae  lea     rcx, [rdi+1Ch]; Buf1
0x1800323b2  mov     r8, r12; Size
0x1800323b5  lea     rdx, [rsp+0D8h+Buf2]; Buf2
0x1800323ba  call    memcmp_0
0x1800323bf  test    eax, eax
0x1800323c1  jns     short loc_1800323C8
0x1800323c3  mov     cl, sil
0x1800323c6  jmp     short loc_1800323CD
0x1800323c8  xor     cl, cl
0x1800323ca  mov     rbx, rdi
0x1800323cd  test    cl, cl
0x1800323cf  lea     rax, [rdi+10h]
0x1800323d3  cmovz   rax, rdi
0x1800323d7  mov     rdi, [rax]
0x1800323da  cmp     byte ptr [rdi+19h], 0
0x1800323de  jz      short loc_1800323AE
0x1800323e0  cmp     byte ptr [rbx+19h], 0
0x1800323e4  jnz     short loc_1800323FB
0x1800323e6  lea     rdx, [rbx+1Ch]; Buf2
0x1800323ea  mov     r8, r12; Size
0x1800323ed  lea     rcx, [rsp+0D8h+Buf2]; Buf1
0x1800323f2  call    memcmp_0
0x1800323f7  test    eax, eax
0x1800323f9  jns     short loc_1800323FE
0x1800323fb  xor     sil, sil
0x1800323fe  test    sil, sil
0x180032401  cmovz   rbx, rbp
0x180032405  cmp     rbx, rbp
0x180032408  jnz     short loc_18003240E
0x18003240a  xor     ebx, ebx
0x18003240c  jmp     short loc_180032411
0x18003240e  mov     ebx, [rbx+60h]
0x180032411  mov     rcx, r14; Resource
0x180032414  call    cs:__imp_RtlReleaseResource
0x18003241a  mov     eax, ebx
0x18003241c  mov     rcx, [rsp+0D8h+var_48]
0x180032424  xor     rcx, rsp; StackCookie
0x180032427  call    __security_check_cookie
0x18003242c  add     rsp, 0A8h
0x180032433  pop     r14
0x180032435  pop     r12
0x180032437  pop     rdi
0x180032438  pop     rsi
0x180032439  pop     rbp
0x18003243a  pop     rbx
0x18003243b  retn
```
