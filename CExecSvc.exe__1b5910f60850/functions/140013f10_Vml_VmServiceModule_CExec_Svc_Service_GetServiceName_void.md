# Vml::VmServiceModule<CExec::Svc::Service>::GetServiceName(void)

- ea: `0x140013f10`
- end: `0x140013f8a`
- name: `?GetServiceName@?$VmServiceModule@VService@Svc@CExec@@@Vml@@QEBAPEBGXZ`
- size: `122`
- prototype: `WCHAR *__fastcall(Vml *)`
- caller_count: `2`
- callee_count: `3`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x1400141b4`
- `0x140014ac0`

## callees

- `0x1400126b0`
- `0x140013bc4`
- `0x140013f10`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_wcscpy_s` at `0x140013f40`
- `api-ms-win-crt-private-l1-1-0!_o_wcscpy_s` at `0x140013f40`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathFindExtensionW` at `0x140013f4d`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathFindExtensionW` at `0x140013f4d`

## string_xrefs

- `0x140013f72`: `onecore\vm\common\vml\VmModules.h`

## pseudocode

```c
WCHAR *__fastcall Vml::VmServiceModule<CExec::Svc::Service>::GetServiceName(Vml *a1)
{
  WCHAR *v1; // rbx
  const unsigned __int16 *CurrentModuleName; // rax
  int v5; // [rsp+20h] [rbp-8h]
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]

  v1 = (WCHAR *)*((_QWORD *)a1 + 18);
  if ( !v1 )
  {
    CurrentModuleName = Vml::GetCurrentModuleName(a1);
    v1 = &`Vml::VmServiceModule<CExec::Svc::Service>::_GetServiceName'::`2'::g_ServiceName;
    if ( (unsigned int)_o_wcscpy_s(
                         &`Vml::VmServiceModule<CExec::Svc::Service>::_GetServiceName'::`2'::g_ServiceName,
                         256,
                         CurrentModuleName) )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0xA38,
        (unsigned int)"onecore\\vm\\common\\vml\\VmModules.h",
        (const char *)0x8007007ALL,
        v5);
    *PathFindExtensionW(&`Vml::VmServiceModule<CExec::Svc::Service>::_GetServiceName'::`2'::g_ServiceName) = 0;
    *((_QWORD *)a1 + 18) = &`Vml::VmServiceModule<CExec::Svc::Service>::_GetServiceName'::`2'::g_ServiceName;
  }
  return v1;
}

```

## disassembly

```asm
0x140013f10  mov     [rsp+arg_0], rbx
0x140013f15  push    rdi; int
0x140013f16  sub     rsp, 20h
0x140013f1a  mov     rbx, [rcx+90h]
0x140013f21  mov     rdi, rcx
0x140013f24  test    rbx, rbx
0x140013f27  jnz     short loc_140013F5F
0x140013f29  call    ?GetCurrentModuleName@Vml@@YAPEBGXZ; Vml::GetCurrentModuleName(void)
0x140013f2e  lea     rbx, ?g_ServiceName@?1??_GetServiceName@?$VmServiceModule@VService@Svc@CExec@@@Vml@@AEBAPEBGXZ@4PAGA; ushort near * `Vml::VmServiceModule<CExec::Svc::Service>::_GetServiceName(void)'::`2'::g_ServiceName
0x140013f35  mov     r8, rax
0x140013f38  mov     rcx, rbx
0x140013f3b  mov     edx, 100h
0x140013f40  call    cs:__imp__o_wcscpy_s
0x140013f46  test    eax, eax
0x140013f48  jnz     short loc_140013F6D
0x140013f4a  mov     rcx, rbx; pszPath
0x140013f4d  call    cs:__imp_PathFindExtensionW
0x140013f53  xor     ecx, ecx
0x140013f55  mov     [rax], cx
0x140013f58  mov     [rdi+90h], rbx
0x140013f5f  mov     rax, rbx
0x140013f62  mov     rbx, [rsp+28h+arg_0]
0x140013f67  add     rsp, 20h
0x140013f6b  pop     rdi
0x140013f6c  retn
0x140013f6d  mov     rcx, [rsp+28h]; this
0x140013f72  lea     r8, aOnecoreVmCommo; "onecore\\vm\\common\\vml\\VmModules.h"
0x140013f79  mov     r9d, 8007007Ah; char *
0x140013f7f  mov     edx, 0A38h; void *
0x140013f84  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
```
