# System.Web.Handlers.ScriptResourceHandler::OutputEmptyPage

- ea: `0x2c460`
- end: `0x2c482`
- name: `System.Web.Handlers.ScriptResourceHandler::OutputEmptyPage`
- size: `34`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config, loader_planting`

## callers

- `0x2c610`

## callees

- `0x2c490`

## string_xrefs

- `0x2c467`: `<!DOCTYPE html PUBLIC "-//W3C//DTD XHTML 1.0 Transitional//EN" "http://www.w3.org/TR/xhtml1/DTD/xhtml1-transitional.dtd">\n<html xmlns="http://www.w3.org/1999/xhtml"><head><script type="text/javascript">parent.Sys.Application._onIFrameLoad();</script><title>`

## pseudocode

```c

```

## disassembly

```asm
0x2c460  ldarg.0
0x2c461  call     void System.Web.Handlers.ScriptResourceHandler::PrepareResponseCache(class [System.Web]System.Web.HttpResponseBase response)
0x2c466  ldarg.0
0x2c467  ldstr    aDoctypeHtmlPub// "<!DOCTYPE html PUBLIC \"-//W3C//DTD XHT"...
0x2c46c  ldarg.1
0x2c46d  call     string [System.Web]System.Web.HttpUtility::HtmlEncode(string)
0x2c472  ldstr    aTitleHeadBodyB// "</title></head><body></body></html>"
0x2c477  call     string [mscorlib]System.String::Concat(string, string, string)
0x2c47c  callvirt instance void [System.Web]System.Web.HttpResponseBase::Write(string)
0x2c481  ret
```
