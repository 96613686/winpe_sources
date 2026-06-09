# SSPI_AUTH_PROVIDER::DiagnoseSSPI(IHttpContext *,int)

- ea: `0x180002084`
- end: `0x18000219e`
- name: `?DiagnoseSSPI@SSPI_AUTH_PROVIDER@@AEAAJPEAVIHttpContext@@H@Z`
- size: `282`
- prototype: `__int64 __fastcall(SSPI_AUTH_PROVIDER *__hidden this, struct IHttpContext *, int)`
- caller_count: `1`
- callee_count: `7`
- tags: `file_ops`

## callers

- `0x1800021f0`

## callees

- `0x180001064`
- `0x180001c34`
- `0x180002084`
- `0x180003654`
- `0x180003ed4`
- `0x180008b6a`
- `0x180009010`

## pseudocode

```c
__int64 __fastcall SSPI_AUTH_PROVIDER::DiagnoseSSPI(SSPI_AUTH_PROVIDER *this, struct IHttpContext *a2)
{
  unsigned int v2; // edi
  __int64 v4; // rbx
  const char *v5; // rax
  const char *v6; // rbp
  const char *v7; // rax
  const char *v8; // rbx
  KERBEROS_INFO *ReferencedKerberosInfo; // rbx
  struct IHttpTraceContext *v10; // rax

  v2 = 0;
  if ( *((_DWORD *)this + 5) )
  {
    v4 = (*(__int64 (__fastcall **)(struct IHttpContext *))(*(_QWORD *)a2 + 24LL))(a2);
    v5 = (const char *)(*(__int64 (__fastcall **)(__int64, __int64, _QWORD))(*(_QWORD *)v4 + 16LL))(v4, 28, 0);
    v6 = v5;
    if ( v5 )
    {
      if ( *v5 )
      {
        v7 = (const char *)(*(__int64 (__fastcall **)(__int64, __int64, _QWORD))(*(_QWORD *)v4 + 16LL))(v4, 24, 0);
        v8 = v7;
        if ( v7 )
        {
          if ( *v7 )
          {
            if ( !strncmp_0(v7, "Negotiate ", 0xAu) )
            {
              if ( strncmp_0(v8 + 10, "TlRMTVNTUA", 0xAu) )
              {
                if ( strncmp_0(v8 + 10, "NTLMSSP", 7u) )
                {
                  ReferencedKerberosInfo = KERBEROS_INFO::GetReferencedKerberosInfo();
                  if ( ReferencedKerberosInfo )
                  {
                    v10 = (struct IHttpTraceContext *)(*(__int64 (__fastcall **)(struct IHttpContext *))(*(_QWORD *)a2 + 272LL))(a2);
                    v2 = KERBEROS_INFO::DoWork(ReferencedKerberosInfo, v10, v6);
                    if ( _InterlockedExchangeAdd((volatile signed __int32 *)ReferencedKerberosInfo, 0xFFFFFFFF) == 1 )
                    {
                      KERBEROS_INFO::~KERBEROS_INFO(ReferencedKerberosInfo);
                      operator delete(ReferencedKerberosInfo);
                    }
                  }
                }
              }
            }
          }
        }
      }
    }
  }
  return v2;
}

```

## disassembly

```asm
0x180002084  push    rbx
0x180002086  push    rbp
0x180002087  push    rsi
0x180002088  push    rdi
0x180002089  sub     rsp, 28h
0x18000208d  xor     edi, edi
0x18000208f  mov     rsi, rdx
0x180002092  cmp     [rcx+14h], edi
0x180002095  jz      loc_180002193
0x18000209b  mov     rax, [rdx]
0x18000209e  mov     rcx, rdx
0x1800020a1  mov     rax, [rax+18h]
0x1800020a5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800020aa  mov     rbx, rax
0x1800020ad  lea     edx, [rdi+1Ch]
0x1800020b0  xor     r8d, r8d
0x1800020b3  mov     rcx, rbx
0x1800020b6  mov     rax, [rax]
0x1800020b9  mov     rax, [rax+10h]
0x1800020bd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800020c2  mov     rbp, rax
0x1800020c5  test    rax, rax
0x1800020c8  jz      loc_180002193
0x1800020ce  cmp     [rax], dil
0x1800020d1  jz      loc_180002193
0x1800020d7  mov     rax, [rbx]
0x1800020da  lea     edx, [rdi+18h]
0x1800020dd  xor     r8d, r8d
0x1800020e0  mov     rcx, rbx
0x1800020e3  mov     rax, [rax+10h]
0x1800020e7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800020ec  mov     rbx, rax
0x1800020ef  test    rax, rax
0x1800020f2  jz      loc_180002193
0x1800020f8  cmp     [rax], dil
0x1800020fb  jz      loc_180002193
0x180002101  lea     r8d, [rdi+0Ah]; MaxCount
0x180002105  mov     rcx, rax; Str1
0x180002108  lea     rdx, Str2; "Negotiate "
0x18000210f  call    strncmp_0
0x180002114  test    eax, eax
0x180002116  jnz     short loc_180002193
0x180002118  lea     r8d, [rdi+0Ah]; MaxCount
0x18000211c  lea     rdx, aTlrmtvntua; "TlRMTVNTUA"
0x180002123  lea     rcx, [rbx+0Ah]; Str1
0x180002127  call    strncmp_0
0x18000212c  test    eax, eax
0x18000212e  jz      short loc_180002193
0x180002130  lea     r8d, [rdi+7]; MaxCount
0x180002134  lea     rdx, aNtlmssp; "NTLMSSP"
0x18000213b  lea     rcx, [rbx+0Ah]; Str1
0x18000213f  call    strncmp_0
0x180002144  test    eax, eax
0x180002146  jz      short loc_180002193
0x180002148  call    ?GetReferencedKerberosInfo@KERBEROS_INFO@@SAPEAV1@XZ; KERBEROS_INFO::GetReferencedKerberosInfo(void)
0x18000214d  mov     rbx, rax
0x180002150  test    rax, rax
0x180002153  jz      short loc_180002193
0x180002155  mov     rax, [rsi]
0x180002158  mov     rcx, rsi
0x18000215b  mov     rax, [rax+110h]
0x180002162  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002167  mov     rdx, rax; struct IHttpTraceContext *
0x18000216a  mov     r8, rbp; char *
0x18000216d  mov     rcx, rbx; this
0x180002170  call    ?DoWork@KERBEROS_INFO@@QEAAJPEAVIHttpTraceContext@@PEBDH@Z; KERBEROS_INFO::DoWork(IHttpTraceContext *,char const *,int)
0x180002175  mov     edi, eax
0x180002177  or      ecx, 0FFFFFFFFh
0x18000217a  lock xadd [rbx], ecx
0x18000217e  cmp     ecx, 1
0x180002181  jnz     short loc_180002193
0x180002183  mov     rcx, rbx; this
0x180002186  call    ??1KERBEROS_INFO@@QEAA@XZ; KERBEROS_INFO::~KERBEROS_INFO(void)
0x18000218b  mov     rcx, rbx; Block
0x18000218e  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180002193  mov     eax, edi
0x180002195  add     rsp, 28h
0x180002199  pop     rdi
0x18000219a  pop     rsi
0x18000219b  pop     rbp
0x18000219c  pop     rbx
0x18000219d  retn
```
