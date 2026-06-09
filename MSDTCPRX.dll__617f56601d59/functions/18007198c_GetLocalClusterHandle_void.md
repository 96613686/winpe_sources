# GetLocalClusterHandle(void)

- ea: `0x18007198c`
- end: `0x180071a2c`
- name: `?GetLocalClusterHandle@@YAPEAU_HCLUSTER@@XZ`
- size: `160`
- prototype: `struct _HCLUSTER *(void)`
- caller_count: `4`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x180013694`
- `0x180018188`
- `0x18001c410`
- `0x1800724e4`

## callees

- `0x18007198c`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800719b5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800719b5`
- `CLUSAPI!ClusterCloseEnum` at `0x1800719cc`
- `CLUSAPI!ClusterCloseEnum` at `0x1800719cc`
- `CLUSAPI!ClusterOpenEnum` at `0x1800719aa`
- `CLUSAPI!ClusterOpenEnum` at `0x1800719aa`
- `CLUSAPI!CloseCluster` at `0x180071a11`
- `CLUSAPI!CloseCluster` at `0x180071a11`
- `CLUSAPI!OpenClusterEx` at `0x1800719ed`
- `CLUSAPI!OpenClusterEx` at `0x1800719ed`

## pseudocode

```c
HCLUSTER GetLocalClusterHandle(void)
{
  HCLUSTER v0; // rbx
  struct _HCLUSENUM *v1; // rax
  bool v2; // di
  HCLUSTER v3; // rax
  struct _HCLUSTER *v4; // rcx

  v0 = hCluster;
  if ( !hCluster )
    goto LABEL_7;
  v1 = ClusterOpenEnum(hCluster, 4u);
  if ( v1 )
  {
    v2 = 1;
    ClusterCloseEnum(v1);
  }
  else
  {
    v2 = GetLastError() != 1722;
  }
  v0 = hCluster;
  if ( !hCluster || !v2 )
  {
LABEL_7:
    v3 = OpenClusterEx(0, 0x2000000u, 0);
    v4 = v3;
    if ( v3 )
    {
      if ( v0 != (HCLUSTER)_InterlockedCompareExchange64(
                             (volatile signed __int64 *)&hCluster,
                             (signed __int64)v3,
                             (signed __int64)v0) )
      {
LABEL_11:
        CloseCluster(v4);
        return hCluster;
      }
      if ( v0 )
      {
        v4 = v0;
        goto LABEL_11;
      }
    }
    return hCluster;
  }
  return v0;
}

```

## disassembly

```asm
0x18007198c  mov     [rsp+arg_0], rbx
0x180071991  push    rdi
0x180071992  sub     rsp, 20h
0x180071996  mov     rbx, cs:hCluster
0x18007199d  test    rbx, rbx
0x1800719a0  jz      short loc_1800719E3
0x1800719a2  mov     edx, 4; dwType
0x1800719a7  mov     rcx, rbx; hCluster
0x1800719aa  call    cs:__imp_ClusterOpenEnum
0x1800719b0  test    rax, rax
0x1800719b3  jnz     short loc_1800719C6
0x1800719b5  call    cs:__imp_GetLastError
0x1800719bb  cmp     eax, 6BAh
0x1800719c0  setnz   dil
0x1800719c4  jmp     short loc_1800719D2
0x1800719c6  mov     rcx, rax; hEnum
0x1800719c9  mov     dil, 1
0x1800719cc  call    cs:__imp_ClusterCloseEnum
0x1800719d2  mov     rbx, cs:hCluster
0x1800719d9  test    rbx, rbx
0x1800719dc  jz      short loc_1800719E3
0x1800719de  test    dil, dil
0x1800719e1  jnz     short loc_180071A1E
0x1800719e3  xor     r8d, r8d; GrantedAccess
0x1800719e6  mov     edx, 2000000h; DesiredAccess
0x1800719eb  xor     ecx, ecx; lpszClusterName
0x1800719ed  call    cs:__imp_OpenClusterEx
0x1800719f3  mov     rcx, rax
0x1800719f6  test    rax, rax
0x1800719f9  jz      short loc_180071A17
0x1800719fb  mov     rax, rbx
0x1800719fe  lock cmpxchg cs:hCluster, rcx
0x180071a07  jnz     short loc_180071A11
0x180071a09  test    rbx, rbx
0x180071a0c  jz      short loc_180071A17
0x180071a0e  mov     rcx, rbx; hCluster
0x180071a11  call    cs:__imp_CloseCluster
0x180071a17  mov     rbx, cs:hCluster
0x180071a1e  mov     rax, rbx
0x180071a21  mov     rbx, [rsp+28h+arg_0]
0x180071a26  add     rsp, 20h
0x180071a2a  pop     rdi
0x180071a2b  retn
```
